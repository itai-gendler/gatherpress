---
kind: primary
routes:
  web: Web
steps:
- text: The Author picks a published venue in the Venue Selector of the event
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts:
    - Name
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product sets the venue of the event
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - Venue
  - entity: venue
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Choose the venue of an event

## Trigger

The event has a place.

## Outcome

The event page shows the venue's name, address and map, and the event appears in that venue's feed.
