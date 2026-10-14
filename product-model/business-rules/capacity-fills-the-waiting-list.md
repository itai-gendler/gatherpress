---
appliesTo:
- type: capability
  id: rsvp-to-event
- type: capability
  id: add-member-rsvp
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp.attending_limit_reached
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
---

# An event never goes past its capacity: once it is full, new attendees join the waiting list

A person counts with their guests. When attending would take an event past its capacity, a new attendee is put on the waiting list instead, and an attendee asking for more guests keeps the guests they had. A capacity of 0 means no limit.
