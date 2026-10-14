---
availability:
- place: web::signed-in
domain: events
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-meta.php#Meta
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php#Event.save_datetimes
- kind: code
  role: implementation
  target: includes/core/classes/event/class-setup.php#Setup.check_waiting_list
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-rsvp-form.php#Rsvp_Form.save_form_schema
- kind: doc
  role: intent
  target: docs/user/creating-and-managing-events.md
---

# Edit event

An organizer changes an event's own details in the event editor: its content, date and time, online link, RSVP settings and RSVP form questions. Saving also promotes people from the waiting list when the change leaves room.
