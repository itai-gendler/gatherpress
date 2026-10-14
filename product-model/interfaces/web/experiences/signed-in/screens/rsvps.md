---
entities:
- entity: rsvp
  shows:
  - Name
  - Email
  - Guests
  - Type
  - Approval
  - Checked in
  - Submitted at
- entity: event
  shows:
  - Title
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-list-table.php
---

# RSVPs

Events > RSVPs in the admin: every RSVP with its attendee, response, type, event, approval, check-in and date, filtered by event, response and approval and searchable.
