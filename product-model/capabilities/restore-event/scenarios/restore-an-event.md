---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Restore for the trashed event
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::events-list
- text: The Product restores the event as a draft
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    from: Trashed
    to: Draft
    facts: []
  contexts:
    web:
      place: web::signed-in::events-list
---

# Restore an event from the trash

## Trigger

A trashed event is wanted after all.

## Outcome

The event is a draft again, with its details and RSVPs.
