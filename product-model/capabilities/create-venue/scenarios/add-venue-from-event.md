---
kind: alternative
routes:
  web: Web
steps:
- text: The Author enters a new venue name and address in the Venue block of the event
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
- text: The Product looks up the coordinates of the address, publishes the venue and sets it as the venue of the event
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: creates
    to: Published
    facts:
    - Name
    - Address
    - Latitude
    - Longitude
  - entity: event
    effect: changes
    facts:
    - Venue
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Add a venue while editing an event

## Trigger

The organizer is editing an event whose place is not a venue yet.

## Outcome

A published venue exists and the event is held there.
