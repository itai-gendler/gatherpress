---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the events archive
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::events-archive
- text: The Product lists published events that have not ended, soonest first
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

# Browse upcoming events

## Trigger

A visitor wants to know what is coming up.

## Outcome

The visitor sees the published events that have not ended yet, soonest first.

## Edge cases

- An event with no date yet appears in neither the upcoming nor the past list.
- With the archive set to None and no page assigned, the events archive address shows a not-found page.
