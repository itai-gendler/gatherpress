---
availability:
- place: web::signed-in
- place: wp-cli
domain: rsvps
references:
- kind: code
  role: implementation
  target: src/blocks/rsvp-response/rsvp-manager.js
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.update_rsvp
- kind: code
  role: implementation
  target: includes/core/classes/commands/class-event-cli.php#Event_Cli.rsvp
- kind: doc
  role: intent
  target: docs/developer/wp-cli/README.md
---

# Add member RSVP

An organizer records a member's response to an event for them, from the attendee manager of the event or with `wp gatherpress event rsvp`. The same capacity, waiting list, guest and anonymity rules apply as when members respond themselves.
