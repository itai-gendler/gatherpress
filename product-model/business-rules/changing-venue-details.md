---
appliesTo:
- type: entity
  id: venue
  effect: changes
  facts:
  - Name
  - Description
  - Address
  - Structured address
  - Latitude
  - Longitude
  - Phone
  - Website
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: writes
    entity: author
- unattended: true
references:
- kind: doc
  role: intent
  target: docs/user/user-roles-and-permissions.md
---

# A venue's details are changed by its author, an editor or an administrator

Editors and administrators change any venue; an author changes the venues they wrote. The background lookup of a saved address is the Product's own.
