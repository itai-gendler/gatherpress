---
appliesTo:
- type: capability
  id: rsvp-to-event
- type: capability
  id: edit-event
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp.check_waiting_list
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/response/class-collection.php#Collection.waiting_list
---

# The waiting list moves up in the order people joined it

When a place opens, because someone stops attending or the capacity is raised, the earliest RSVPs on the waiting list become attending while places remain; with no capacity everyone on it does. The person promoted is not emailed.
