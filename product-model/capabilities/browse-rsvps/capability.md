---
availability:
- place: web::signed-in
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-list-table.php#List_Table
- kind: code
  role: implementation
  target: src/rsvp-admin/index.js
---

# Browse RSVPs

An editor looks through the RSVPs of every event under Events > RSVPs, filtering by event, response and approval and searching by name, email or IP address.
