---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs wp gatherpress settings export with a file name
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: wp-cli
- text: The Product writes the settings to the file
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

# Export the settings from the command line

## Trigger

An operator scripts a backup.

## Outcome

The settings are printed or written to the file named.
