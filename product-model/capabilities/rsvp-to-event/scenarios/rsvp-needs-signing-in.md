---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor chooses RSVP on the event page
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
- text: The Product shows the login prompt and records nothing
  kind: condition
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::event-page
---

# RSVP while signed out

## Trigger

A visitor without a link chooses RSVP on an event that takes RSVPs from members.

## Outcome

Nothing is recorded; the visitor is asked to log in or register.
