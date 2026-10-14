---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor submits an RSVP for an event that has ended
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
- text: The Product refuses it with Registration for this event is now closed
  kind: condition
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - End
  contexts:
    web:
      place: web::public::event-page
---

# The RSVP form is closed

## Trigger

A visitor reaches an event whose RSVP form no longer accepts responses: Open RSVP is off, RSVP is off, or the event has ended.

## Outcome

No RSVP is recorded; the form is not shown, or a direct submission is refused with the reason.
