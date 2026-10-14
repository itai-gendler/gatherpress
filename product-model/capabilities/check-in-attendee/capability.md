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

# Check in attendee

An editor marks an approved RSVP as checked in at the event, one at a time or in bulk.
