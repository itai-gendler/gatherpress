---
entities:
- entity: event
  shows:
  - Title
  - Start
  - End
  - Timezone
  - Venue
  - Topics
- entity: rsvp
  shows:
  - Approval
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-admin-list.php
---

# Events list

All Events in the admin, with Upcoming and Past views, each event's date and time, venue and RSVP count with unapproved RSVPs flagged.
