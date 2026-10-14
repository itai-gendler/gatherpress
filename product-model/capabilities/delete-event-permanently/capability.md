---
availability:
- place: web::signed-in
domain: events
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-setup.php#Setup.delete_event
---

# Delete event permanently

An organizer deletes a trashed event for good, together with its RSVPs.
