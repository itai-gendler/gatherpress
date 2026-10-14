---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Export on the Tools tab
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::tools
- text: The Product hands over the settings as a file
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: reads
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

# Export the settings to a file

## Trigger

An administrator is setting up a second community site.

## Outcome

The administrator has a file of the GatherPress settings that differ from their defaults.
