---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor submits the RSVP form with an email that already responded to the event
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product refuses the form with You've already RSVP'd to this event
  kind: condition
  actor: visitor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Email
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
---

# A second RSVP with the same email is refused

## Trigger

A visitor submits the RSVP form with an email that already responded to the event.

## Outcome

Nothing new is recorded; the visitor is told they already RSVP'd.
