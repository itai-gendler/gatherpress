---
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-user.php#User.save_profile_fields
- kind: code
  role: implementation
  target: includes/templates/admin/user/notifications.php
- kind: code
  role: implementation
  target: includes/templates/admin/user/date-time.php
- kind: doc
  role: intent
  target: docs/user/privacy.md
---

# Change profile settings

A signed-in person chooses in their profile whether they receive event emails from organizers and how event times are shown to them: a 12-hour or 24-hour clock and their own timezone.
