---
appliesTo:
- type: entity
  id: event
  effect: changes
  to: Scheduled
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

# An event is scheduled by its author, an editor or an administrator

Scheduling follows the same permission as publishing.
