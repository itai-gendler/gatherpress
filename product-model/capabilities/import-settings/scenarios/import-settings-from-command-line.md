---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs wp gatherpress settings import with the file and --apply
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: wp-cli
- text: The Product applies the settings from the file
  kind: product
  actor: operator
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
    cli:
      place: wp-cli
---

# Import settings from the command line

## Trigger

An operator applies a settings file to a site.

## Outcome

Without --apply the command only reports what would change; with it the settings are applied, merged or replacing the rest.
