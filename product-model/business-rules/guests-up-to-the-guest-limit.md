---
appliesTo:
- type: capability
  id: rsvp-to-event
- type: capability
  id: add-member-rsvp
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp
- kind: doc
  role: context
  target: docs/developer/data-model/README.md
---

# An attendee brings at most the event's guest limit of guests

Asking for more guests than allowed records the allowed number rather than refusing the RSVP. Anyone on the waiting list or not attending has no guests.
