---
appliesTo:
- type: entity
  id: rsvp
  effect: changes
  facts:
  - Checked in
permits:
- actors:
  - editor
  - administrator
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-list-table.php#List_Table.process_bulk_action
---

# Attendees are checked in by editors and administrators

Check-in is an action of the RSVPs page.
