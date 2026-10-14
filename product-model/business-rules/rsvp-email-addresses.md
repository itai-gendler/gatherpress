---
appliesTo:
- type: entity
  id: rsvp
  effect: reads
  facts:
  - Email
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: receives
    entity: event
  - verb: writes
    entity: author
- related:
  - verb: sends
    entity: visitor
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/response/class-serializer.php#Serializer.to_array
---

# An RSVP's email address is read only by editors, administrators, the event's author when emailing its attendees, and the person who sent it

The RSVPs page shows email addresses to those who moderate RSVPs. When an event's author emails its attendees the Product uses the addresses without showing them, and the confirmation email goes to the address the person gave.
