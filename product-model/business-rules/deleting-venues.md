---
appliesTo:
- type: entity
  id: venue
  effect: removes
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

# A venue is deleted permanently by its author, an editor or an administrator

Permanent deletion follows the same permission as trashing.
