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
  target: includes/core/classes/rsvp/class-form.php#Form.has_duplicate_rsvp
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-storage.php#Storage.get
---

# Each person has at most one RSVP per event

A member responding again changes their RSVP; a visitor sending the form again with the same email, or with the email of an existing account that already responded, is refused.
