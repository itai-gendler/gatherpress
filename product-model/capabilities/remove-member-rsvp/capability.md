---
availability:
- place: web::signed-in
domain: rsvps
references:
- kind: code
  role: implementation
  target: src/blocks/rsvp-response/rsvp-manager.js
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-storage.php#Storage.save
---

# Remove member RSVP

An organizer takes a member off an event's responses in the attendee manager of the event, deleting the RSVP.
