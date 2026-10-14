---
appliesTo:
- type: entity
  id: site-settings
  effect: changes
permits:
- actors:
  - administrator
- actors:
  - operator
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-settings.php#Settings
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-tools.php#Tools
---

# GatherPress settings are changed by administrators or an operator

The settings tabs need the permission to manage the site's options; an operator imports settings from the command line.
