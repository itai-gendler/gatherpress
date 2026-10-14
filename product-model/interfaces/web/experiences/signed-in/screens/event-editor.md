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
  - Topics
  - Online event
  - Online event link
  - RSVP enabled
  - Open RSVP
  - Anonymous RSVP
  - Capacity
  - Guest limit
  - RSVP form questions
  - Publish date
  collects:
  - Title
  - Description
  - Start
  - End
  - Timezone
  - All day
  - Append time zone
  - Venue
  - Topics
  - Online event
  - Online event link
  - RSVP enabled
  - Open RSVP
  - Anonymous RSVP
  - Capacity
  - Guest limit
  - RSVP form questions
  - Publish date
- entity: venue
  shows:
  - Name
  - Address
  collects:
  - Name
  - Address
- entity: topic
  shows:
  - Name
- entity: rsvp
  shows:
  - Name
  - Guests
- entity: account
  shows:
  - Display name
references:
- kind: code
  role: implementation
  target: src/panels/event-settings/index.js
- kind: code
  role: implementation
  target: src/panels/rsvp-settings/index.js
- kind: code
  role: implementation
  target: src/blocks/rsvp-response/rsvp-manager.js
- kind: code
  role: implementation
  target: src/components/EmailNotificationManager.js
---

# Event editor

The block editor for one event, with its event settings: date and time, venue, online link, RSVP settings, topics, the attendee manager and the email composer.
