---
appliesTo:
- type: entity
  id: rsvp
  effect: creates
permits:
- actors:
  - subscriber
- actors:
  - visitor
  when:
  - entity: site-settings
    fact: Open RSVP
    is: 'On'
  - entity: event
    fact: Open RSVP
    is: 'On'
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
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp.allows_open_rsvp
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.update_rsvp
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
---

# An RSVP is made by the person responding or recorded by an organizer

A signed-in person RSVPs for themselves. A visitor RSVPs without an account only while Open RSVP is on for the site and for the event. An event's author, an editor or an administrator records a member's RSVP for them, and an operator does so from the command line.
