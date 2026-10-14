---
appliesTo:
- type: capability
  id: rsvp-to-event
- type: capability
  id: rsvp-without-account
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php#Event.has_event_past
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-form.php#Form.preprocess_rsvp_comment
---

# RSVPs cannot be made or changed on the site once the event has ended

After its end the RSVP block shows the event as past and the RSVP form refuses submissions.
