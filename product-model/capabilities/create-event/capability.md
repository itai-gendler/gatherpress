---
availability:
- place: web::signed-in
domain: events
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-setup.php#Setup
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp
- kind: code
  role: implementation
  target: includes/core/templates/event/event-with-rsvp.php
- kind: doc
  role: intent
  target: docs/user/creating-and-managing-events.md
---

# Create event

An organizer starts a new event from Events > Add New. It begins as a draft dated the next day at 6 pm for two hours, with the site's RSVP defaults and a starter layout of the date, calendar links, venue, online link, RSVP and attendee list.
