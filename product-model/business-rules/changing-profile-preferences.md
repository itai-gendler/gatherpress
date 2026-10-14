---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Event updates
  - Time format
  - Timezone
permits:
- related:
  - verb: signs in with
    entity: subscriber
- related:
  - verb: signs in with
    entity: author
- related:
  - verb: signs in with
    entity: editor
- related:
  - verb: signs in with
    entity: administrator
- actors:
  - administrator
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-user.php#User.save_profile_fields
---

# A person's event preferences are changed by that person or an administrator

Everyone keeps their own profile; administrators may edit other people's.
