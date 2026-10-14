---
kind: alternative
routes:
  web: Web
steps:
- text: The Author clears the Venue Selector of the event
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product removes the venue from the event
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - Venue
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Leave an event without a venue

## Trigger

The event no longer happens at a physical place, or the place is not known yet.

## Outcome

The event has no venue and shows none.
