---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Organizer
permits:
- actors:
  - administrator
references:
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-roles.php#Roles
---

# Only administrators list people as Organizers

The Organizers list lives on the Roles tab of the settings.
