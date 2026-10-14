---
appliesTo:
- type: entity
  id: event
  effect: changes
  to: Trashed
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

# An event is trashed by its author, an editor or an administrator

Moving an event to the trash follows the WordPress permission to delete it.
