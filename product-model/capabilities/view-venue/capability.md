---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-venue.php
- kind: code
  role: implementation
  target: includes/core/classes/venue/map/class-map.php
- kind: doc
  role: intent
  target: docs/user/blocks/venue-v2/README.md
---

# View venue

Anyone reads a venue's page: its name, address, phone, website, description and map.
