---
kind: primary
routes:
  web: Web
steps:
- text: The Author types the address of the venue and picks one of the suggested addresses
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::venue-editor
- text: The Product saves the address and its coordinates
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: changes
    facts:
    - Address
    - Latitude
    - Longitude
  contexts:
    web:
      place: web::signed-in::venue-editor
---

# Change a venue's address

## Trigger

The venue moved, or its address was wrong.

## Outcome

The venue has the new address and coordinates, and every event held there shows them.

## Edge cases

- The coordinates can be entered by hand instead of taken from the address.
