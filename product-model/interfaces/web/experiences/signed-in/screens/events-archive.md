---
entities:
- entity: event
  shows:
  - Title
  - Start
  - End
  - Timezone
  - Venue
- entity: account
  shows:
  - Timezone
  - Time format
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-query.php
---

# Events archive

The site's list of events: upcoming events soonest first, or past events most recent first, as the site is set up, including pages chosen to hold either list.
