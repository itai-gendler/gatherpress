---
appliesTo:
- type: capability
  id: rsvp-without-account
- type: capability
  id: confirm-rsvp
- type: capability
  id: view-attendees
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-storage.php#Storage.all
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-form.php#Form.process_rsvp
---

# Only approved RSVPs count and are listed

Attendee lists, counts, capacity and the waiting list consider approved RSVPs only. An RSVP sent without an account starts pending and counts once its link is followed or an editor approves it.
