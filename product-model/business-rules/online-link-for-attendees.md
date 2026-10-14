---
appliesTo:
- type: entity
  id: event
  effect: reads
  facts:
  - Online event link
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php#Event.maybe_get_online_event_link
- kind: doc
  role: intent
  target: docs/user/blocks/online-event.md
---

# The online event link is shown only to its attendees, and only until the event ends

People not attending see that the event is online and that the link is for attendees; after the event ends nobody on the site sees the link. Organizers editing the event always see it.

## Rationale

An open meeting link on a public page gets found and rooms get crashed; requiring an RSVP means organizers know who is joining.
