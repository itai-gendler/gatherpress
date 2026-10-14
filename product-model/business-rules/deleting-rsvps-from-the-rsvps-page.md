---
appliesTo:
- type: entity
  id: rsvp
  effect: removes
  contexts:
  - place: web::signed-in::rsvps
permits:
- actors:
  - editor
  - administrator
- unattended: true
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-list-table.php#List_Table.process_bulk_action
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-cleanup.php#Cleanup
---

# RSVPs are deleted from the RSVPs page by editors and administrators

Deleting from the RSVPs page needs the permission to moderate comments. The Product's scheduled cleanup deletes unconfirmed RSVPs there too.
