---
appliesTo:
- type: entity
  id: rsvp
  effect: removes
  contexts:
  - place: web::signed-in::event-editor
permits:
- related:
  - verb: receives
    entity: event
  - verb: writes
    entity: author
- actors:
  - editor
  - administrator
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.update_rsvp
---

# A member's RSVP is removed in the event editor by the event's organizers

The event's author, editors and administrators take members off its responses from the attendee manager.
