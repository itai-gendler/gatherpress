---
availability:
- place: web::signed-in
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-list-table.php#List_Table.process_bulk_action
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
---

# Unapprove RSVP

An editor sets an approved RSVP back to pending, so it no longer counts or is listed.
