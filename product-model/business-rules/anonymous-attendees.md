---
appliesTo:
- type: entity
  id: rsvp
  effect: reads
  facts:
  - Name
permits:
- actors:
  - editor
  - administrator
- actors:
  - visitor
  - subscriber
  - author
  when:
  - fact: Anonymous
    is: 'Off'
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/response/class-serializer.php#Serializer.to_array
---

# Only editors and administrators see who an anonymous attendee is

Everyone sees the names of attendees who did not ask to be anonymous; an anonymous attendee appears as Anonymous with a placeholder avatar to everyone but editors and administrators.
