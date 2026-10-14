---
appliesTo:
- type: entity
  id: venue
  effect: changes
  to: Published
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: writes
    entity: author
references:
- kind: doc
  role: intent
  target: docs/user/user-roles-and-permissions.md
---

# A venue is published by its author, an editor or an administrator

Publishing a venue follows the WordPress permission to publish posts.
