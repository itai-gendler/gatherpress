---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-event-date.php
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php#Event.get_display_datetime
- kind: doc
  role: intent
  target: docs/user/blocks/event-date.md
---

# View event

Anyone reads an event's page: its date and time, venue with address and map, description and everything the organizer arranged on it.
