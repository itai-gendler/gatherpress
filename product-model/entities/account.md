---
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-user.php
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-roles.php
---

# Account

A person's WordPress user account, as GatherPress uses it: who they are, where event email reaches them and how event times are shown to them.

## Information kept

- **Display name** — the name shown for them on attendee lists
- **Email** — where event email reaches them
- **Event updates** — whether they receive event emails from organizers; on until they turn it off, unless the site changes that default
- **Time format** — Default, 12-hour or 24-hour, overriding the site's time format for event times shown to them
- **Timezone** — a timezone in which event times are shown to them on the site, or Default to show each event in its own timezone
- **Organizer** — whether the site lists them as an Organizer, shown as their role on attendee lists ahead of members
