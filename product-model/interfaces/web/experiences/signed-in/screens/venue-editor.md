---
entities:
- entity: venue
  shows:
  - Name
  - Description
  - Address
  - Phone
  - Website
  - Latitude
  - Longitude
  - Structured address
  collects:
  - Name
  - Description
  - Address
  - Phone
  - Website
  - Latitude
  - Longitude
references:
- kind: code
  role: implementation
  target: src/panels/venue-settings/index.js
- kind: code
  role: implementation
  target: src/components/AddressAutocompleteField/index.js
---

# Venue editor

The block editor for one venue, with its address, phone, website and coordinates and the venue map.
