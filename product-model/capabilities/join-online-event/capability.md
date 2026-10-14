---
availability:
- place: web::signed-in
- place: web::public
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php#Event.maybe_get_online_event_link
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-online-event.php
- kind: doc
  role: intent
  target: docs/user/blocks/online-event.md
---

# Join online event

An attendee of an online event finds its joining link on the event page; everyone else sees that the link is for attendees.
