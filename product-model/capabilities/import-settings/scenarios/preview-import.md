---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs wp gatherpress settings import with the file and no --apply
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: wp-cli
- text: The Product reports what would change and leaves the settings as they are
  kind: product
  actor: operator
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
    cli:
      place: wp-cli
---

# Preview an import

## Trigger

An operator wants to know what a settings file would change.

## Outcome

The command lists the changes and applies nothing.
