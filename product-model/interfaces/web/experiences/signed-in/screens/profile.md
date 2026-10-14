---
entities:
- entity: account
  shows:
  - Event updates
  - Time format
  - Timezone
  collects:
  - Event updates
  - Time format
  - Timezone
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-user.php
---

# Profile

The person's WordPress profile, where GatherPress adds their event email preference and how event times are shown to them.
