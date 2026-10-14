---
appliesTo:
- type: capability
  id: view-event
- type: capability
  id: edit-event
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php#Event.is_all_day
- kind: doc
  role: intent
  target: docs/user/creating-and-managing-events.md
---

# An all-day event shows the same dates in every timezone

An all-day date carries no time, so it is never converted for a visitor or member in another timezone.
