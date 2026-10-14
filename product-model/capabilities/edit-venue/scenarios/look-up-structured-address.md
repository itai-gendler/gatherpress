---
kind: unattended
routes:
  web: Web
steps:
- text: A saved venue address has not been looked up yet
  kind: condition
  unattended: true
  entities:
  - entity: venue
    effect: reads
    facts:
    - Address
  contexts:
    web:
      place: web::signed-in::venue-editor
- text: The Product looks the address up with the geocoding service and stores its parts
  kind: product
  entities:
  - entity: site-settings
    effect: reads
    facts:
    - Geocoding service
    - Country code filter
  - entity: venue
    effect: changes
    facts:
    - Structured address
  contexts:
    web:
      place: web::signed-in::venue-editor
---

# Look up the parts of a venue's address

## Trigger

A venue address was saved and has not been looked up yet.

## Outcome

The venue keeps its street, city, postcode, country and the rest of its address as separate parts.

## Edge cases

- When the geocoding service fails the parts are left as they were; clearing the address clears them.
