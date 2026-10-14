---
availability:
- place: web::signed-in
domain: venues
references:
- kind: code
  role: implementation
  target: includes/core/classes/venue/class-meta.php#Meta
- kind: code
  role: implementation
  target: includes/core/classes/class-geo-sync.php#Geo_Sync
- kind: code
  role: implementation
  target: includes/core/classes/class-geocoding.php#Geocoding
- kind: doc
  role: intent
  target: docs/user/venues.md
- kind: doc
  role: context
  target: docs/developer/venue-address-format.md
---

# Edit venue

An organizer changes a venue's details. Every event held there shows the change. The address field suggests real addresses as it is typed, and once an address is saved the Product looks up its structured parts in the background.
