---
availability:
- place: web::signed-in
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-cleanup.php#Cleanup.rsvp_cleanup
- kind: doc
  role: intent
  target: docs/configuration.md
---

# Remove unconfirmed RSVPs

While RSVP cleanup is on, the Product regularly deletes RSVPs that are pending approval and were sent more than a day ago.
