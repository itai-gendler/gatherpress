---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor submits the RSVP form with a required question empty
  kind: actor
  actor: visitor
  entities:
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product refuses the form and marks each field at fault
  kind: condition
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - RSVP form questions
  contexts:
    web:
      place: web::public::event-page
---

# An RSVP with a missing or invalid answer is refused

## Trigger

A visitor submits the RSVP form leaving a required question empty or giving an answer that does not fit its type.

## Outcome

Nothing is recorded and no email is sent; each field at fault is marked with what to fix.
