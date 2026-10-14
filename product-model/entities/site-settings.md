---
singleton: true
domain: settings
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-settings.php
- kind: doc
  role: intent
  target: docs/configuration.md
---

# Site settings

The GatherPress settings the site keeps once, under Events > Settings.

## Information kept

- **Date format** — how event dates are displayed
- **Time format** — how event times are displayed
- **Show timezone** — whether the timezone is shown next to event times
- **Event date as publish date** — whether the event's date replaces the publish date wherever WordPress shows a post date
- **Event archive** — what the events archive shows with no page assigned: upcoming events, past events or nothing
- **Upcoming events page** — the page that holds the list of upcoming events
- **Past events page** — the page that holds the list of past events
- **Events permalink** — the address base of event pages
- **Topics permalink** — the address base of topic pages
- **Mapping platform** — OpenStreetMap or Google Maps
- **Custom tile layer** — a tile server URL and attribution replacing the default map tiles
- **CARTO API key** — the key the default OpenStreetMap tiles need
- **Google Maps API key** — the key for Google Maps
- **Map defaults** — render mode, zoom, size, aspect ratio, scale and map type given to newly added venue maps
- **Geocoding service** — the address lookup service used for venue autocomplete and geocoding
- **Country code filter** — the countries address lookups are limited to
- **Venues permalink** — the address base of venue pages
- **RSVP mode** — All events, Per event (default on), Per event (default off) or Disabled
- **Open RSVP** — whether visitors without an account may RSVP anywhere on the site
- **Default capacity** — the capacity new events start with
- **Default guest limit** — the guest limit new events start with
- **Anonymous RSVP default** — whether new events let people be listed as anonymous
- **RSVP cleanup** — whether unconfirmed RSVPs are removed automatically
- **Cleanup frequency** — the unit of the cleanup schedule: hourly, daily, weekly, monthly or yearly
- **Cleanup interval** — how many of those units pass between cleanups
