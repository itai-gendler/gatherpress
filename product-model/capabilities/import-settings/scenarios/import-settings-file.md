---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator uploads an exported file on the Tools tab, chooses Merge, checks the import preview and imports
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::tools
- text: The Product applies the settings from the file, keeping the ones it does not mention
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: changes
    facts:
    - Date format
    - Time format
    - Show timezone
    - Event date as publish date
    - Event archive
    - Upcoming events page
    - Past events page
    - Events permalink
    - Topics permalink
    - Mapping platform
    - Custom tile layer
    - CARTO API key
    - Google Maps API key
    - Map defaults
    - Geocoding service
    - Country code filter
    - Venues permalink
    - RSVP mode
    - Open RSVP
    - Default capacity
    - Default guest limit
    - Anonymous RSVP default
    - RSVP cleanup
    - Cleanup frequency
    - Cleanup interval
  contexts:
    web:
      place: web::administration::tools
---

# Import settings from a file

## Trigger

An administrator copies the configuration of another site.

## Outcome

The settings in the file are in force; settings the file does not mention are kept.
