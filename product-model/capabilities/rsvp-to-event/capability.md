---
availability:
- place: web::signed-in
- place: web::public
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp.process
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp.check_waiting_list
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.update_rsvp
- kind: code
  role: implementation
  target: src/blocks/rsvp/view.js
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
- kind: doc
  role: intent
  target: docs/user/blocks/rsvp-and-inner-blocks.md
---

# RSVP to event

A person says whether they are coming to an event from its RSVP button, with how many guests and whether to be listed as anonymous, and changes that answer later the same way. Members respond with their account; a person who responded without one changes their answer from the event page opened through their emailed link. When the event is full a new attendee joins the waiting list, and when someone stops attending the people who waited longest move up.
