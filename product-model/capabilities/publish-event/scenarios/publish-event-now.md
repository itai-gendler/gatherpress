---
kind: primary
routes:
  web: Web
steps:
- text: The Author publishes the event
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product makes the event live on the site
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    from: Draft
    to: Published
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Publish an event now

## Trigger

The event is ready to announce.

## Outcome

The event is live: on its page, in the events archive and lists, and in the calendar feeds while it is upcoming.
