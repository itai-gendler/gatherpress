---
appliesTo:
- type: capability
  id: send-event-update
- type: capability
  id: change-profile-settings
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-user.php#User.has_event_updates_opt_in
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.send_event_email_to_recipient
- kind: doc
  role: intent
  target: docs/user/privacy.md
---

# Event emails go only to people who have not turned off event updates

Members are opted in until they untick event updates in their profile; a person without an account is skipped when they declined updates on the RSVP form.
