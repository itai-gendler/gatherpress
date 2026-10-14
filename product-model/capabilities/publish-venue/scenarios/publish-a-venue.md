---
kind: primary
routes:
  web: Web
steps:
- text: The Author publishes the venue
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::venue-editor
- text: The Product makes the venue live and offers it in the Venue Selector
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: changes
    from: Draft
    to: Published
    facts: []
  contexts:
    web:
      place: web::signed-in::venue-editor
---

# Publish a venue

## Trigger

A drafted venue is ready to use.

## Outcome

The venue has its own page and feed and appears in the Venue Selector of every event.
