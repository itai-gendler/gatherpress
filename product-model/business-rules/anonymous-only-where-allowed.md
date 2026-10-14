---
appliesTo:
- type: capability
  id: rsvp-to-event
- type: capability
  id: rsvp-without-account
- type: capability
  id: add-member-rsvp
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp
---

# An RSVP is anonymous only where the event allows anonymous RSVPs

Asking to be listed as anonymous on an event that does not allow it records a named RSVP.
