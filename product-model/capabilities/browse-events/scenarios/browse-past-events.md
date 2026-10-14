---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens the page the site set for past events
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::events-archive
- text: The Product lists published events that have ended, most recent first
  kind: product
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - End
    - Timezone
    - Venue
  contexts:
    web:
      place: web::public::events-archive
---

# Browse past events

## Trigger

A visitor looks back at what the community has done.

## Outcome

The visitor sees events that have ended, most recent first.
