---
availability:
- place: web::signed-in
domain: events
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.send_emails
- kind: code
  role: implementation
  target: includes/templates/admin/emails/event-email.php
- kind: code
  role: implementation
  target: src/components/EmailNotificationManager.js
- kind: doc
  role: intent
  target: docs/user/emails.md
---

# Send event update

An organizer composes a message about an event and emails it to the event's attendees, the people on its waiting list, those not attending, or every member of the site. Each email carries the message, the event's image, title, date and venue, an RSVP Now link while the event still takes RSVPs, and its excerpt; it is sent in the background through the site's mail.
