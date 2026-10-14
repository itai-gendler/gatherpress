---
entities:
- entity: site-settings
  shows: &id001
  - Mapping platform
  - Custom tile layer
  - CARTO API key
  - Google Maps API key
  - Map defaults
  - Geocoding service
  - Country code filter
  - Venues permalink
  collects: *id001
references:
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-venues.php
---

# Venues settings

The Venues tab: mapping platform, map tiles and keys, defaults for new venue maps, geocoding and the venue permalink.
