---
appliesTo:
- type: entity
  id: event
  effect: changes
  to: Draft
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

# A trashed event is restored by its author, an editor or an administrator

Restoring follows the same permission as trashing.
