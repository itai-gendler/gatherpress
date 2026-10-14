---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor follows a confirmation link the Product does not recognise
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product changes nothing and shows the event page
  kind: condition
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::public::event-page
---

# A confirmation link that is not recognised

## Trigger

A visitor opens an event from a link whose code does not match an RSVP awaiting it.

## Outcome

Nothing changes; the event page shows as it does to anyone.
