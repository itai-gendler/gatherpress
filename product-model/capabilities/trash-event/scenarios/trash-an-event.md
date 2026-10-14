---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Trash for the event
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
- text: The Product moves the event to the trash
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    from: Published
    to: Trashed
    facts: []
  contexts:
    web:
      place: web::signed-in::events-list
---

# Trash an event

## Trigger

An event is cancelled or was created by mistake.

## Outcome

The event is in the trash and off the site, with its RSVPs kept.
