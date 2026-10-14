---
kind: primary
routes:
  web: Web
steps:
- text: The Author sets a new start, a duration or end and a timezone in the event settings
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product saves the new times and lists the event under them
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - Start
    - End
    - Timezone
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Reschedule an event

## Trigger

The event moves to another date or time.

## Outcome

The event shows the new date and time everywhere it is listed; existing RSVPs are kept.
