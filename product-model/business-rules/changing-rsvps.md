---
appliesTo:
- type: entity
  id: rsvp
  effect: changes
permits:
- related:
  - verb: sends
    entity: subscriber
- related:
  - verb: sends
    entity: visitor
- related:
  - verb: receives
    entity: event
  - verb: writes
    entity: author
- actors:
  - editor
  - administrator
- actors:
  - operator
- unattended: true
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.rsvp_route
---

# An RSVP is changed by the person who sent it or by the organizers of its event

People change their own response, members with their account and others through their emailed link; the event's author, editors and administrators change anyone's; an operator records changes from the command line. Moving the waiting list up is the Product's own.
