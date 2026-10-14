---
entities:
- entity: event
  shows:
  - Title
  - Description
  - Start
  - End
  - Timezone
  - All day
  - Append time zone
  - Venue
  - Online event
  - Online event link
  - Guest limit
  - Anonymous RSVP
  - RSVP form questions
- entity: venue
  shows:
  - Name
  - Address
  - Latitude
  - Longitude
- entity: rsvp
  shows:
  - Name
  - Guests
  - Anonymous
  - Approval
  collects:
  - Guests
  - Anonymous
- entity: account
  shows:
  - Timezone
  - Time format
references:
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-rsvp.php
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-rsvp-response.php
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-online-event.php
---

# Event page

One event as the site shows it: its date and time, venue and map, online link for attendees, RSVP controls, attendee list and calendar links.
