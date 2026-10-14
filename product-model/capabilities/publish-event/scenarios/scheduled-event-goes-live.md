---
kind: unattended
routes:
  web: Web
steps:
- text: The publish date of a scheduled event has arrived
  kind: condition
  unattended: true
  entities:
  - entity: event
    effect: reads
    facts:
    - Publish date
  contexts:
    web:
      place: web::signed-in::events-list
- text: The Product publishes the event
  kind: product
  entities:
  - entity: event
    effect: changes
    from: Scheduled
    to: Published
    facts: []
  contexts:
    web:
      place: web::signed-in::events-list
---

# A scheduled event goes live

## Trigger

The publish date of a scheduled event arrives.

## Outcome

The event is live on the site.
