---
kind: alternative
routes:
  web: Web
steps:
- text: The Author sets a future publish date and schedules the event
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product schedules the event for that publish date
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    from: Draft
    to: Scheduled
    facts:
    - Publish date
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Schedule an event to go live

## Trigger

The organizer wants the announcement to appear later.

## Outcome

The event is scheduled and goes live at the chosen publish date.
