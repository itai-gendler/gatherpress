---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Add New under Venues and enters the name, address, phone and website
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::venue-editor
- text: The Product creates the venue as a draft with coordinates looked up from the address
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: creates
    to: Draft
    facts:
    - Name
    - Description
    - Address
    - Latitude
    - Longitude
    - Phone
    - Website
  contexts:
    web:
      place: web::signed-in::venue-editor
---

# Add a venue

## Trigger

The community meets at a new place.

## Outcome

A draft venue exists with its name, address, coordinates, phone and website.
