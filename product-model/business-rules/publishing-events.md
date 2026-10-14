---
appliesTo:
- type: entity
  id: event
  effect: changes
  to: Published
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

# An event is published by its author, an editor or an administrator

An author publishes their own events; editors and administrators publish any. A scheduled event goes live on its own at its publish date.
