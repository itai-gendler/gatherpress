---
kind: validation
routes:
  web: Web
steps:
- text: The Subscriber opens the event page of an ended event
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - End
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product shows Past Event in place of the RSVP button and records nothing
  kind: condition
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - End
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
---

# RSVP after the event ended

## Trigger

A member opens an event that has already ended.

## Outcome

The RSVP block shows the event as past and no response can be made or changed.
