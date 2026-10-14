---
type: api
actors:
- calendar-app
entryPoints:
- api: /feed/ical
- api: /event/feed/ical
- api: /venue/<venue-slug>/feed/ical
- api: /topic/<topic-slug>/feed/ical
references:
- kind: code
  role: implementation
  target: includes/core/classes/calendar/class-setup.php
- kind: doc
  role: intent
  target: docs/user/calendar-feeds.md
---

# Calendar feeds

The iCalendar feed addresses a calendar app subscribes to, for the whole site, the events archive, one venue or one topic; the app checks them periodically to stay current.
