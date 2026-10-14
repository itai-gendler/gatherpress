---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks Google Maps as mapping platform, enters the API key and saves the tab
  kind: actor
  actor: administrator
  entities:
  - entity: site-settings
    effect: reads
    facts:
    - Mapping platform
  contexts:
    web:
      place: web::administration::venues-settings
- text: The Product saves the venues settings
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: changes
    facts:
    - Mapping platform
    - Custom tile layer
    - CARTO API key
    - Google Maps API key
    - Map defaults
    - Geocoding service
    - Country code filter
    - Venues permalink
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::venues-settings
---

# Switch venue maps to Google Maps

## Trigger

The community prefers Google Maps.

## Outcome

Venue maps are drawn with Google Maps using the key given; maps already placed keep their own size and zoom.

## Edge cases

- Changing a map default affects only venue maps added afterwards.
