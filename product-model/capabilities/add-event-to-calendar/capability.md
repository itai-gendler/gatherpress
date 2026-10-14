---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/core/classes/calendar/class-calendar.php
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-add-to-calendar.php
- kind: doc
  role: intent
  target: docs/user/blocks/add-to-calendar.md
---

# Add event to calendar

Anyone saves one event into their own calendar from the Add to Calendar choices: an iCal or Outlook file, or Google Calendar or Yahoo Calendar prefilled with the event. The copy is a snapshot that does not follow later changes.
