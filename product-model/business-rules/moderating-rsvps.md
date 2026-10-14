---
appliesTo:
- type: entity
  id: rsvp
  effect: changes
  facts:
  - Approval
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: sends
    entity: visitor
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-list-table.php#List_Table.process_bulk_action
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp
---

# RSVPs are approved, held or marked as spam by editors and administrators

The RSVPs page and its approval actions need the WordPress permission to moderate comments, which editors and administrators hold. A person who RSVPed without an account approves their own RSVP by following the emailed link.
