---
availability:
- place: web::public
- place: web::signed-in
domain: events
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-query.php#Query
- kind: code
  role: implementation
  target: includes/core/classes/event/class-admin-list.php#Admin_List
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-event-query.php
- kind: doc
  role: intent
  target: docs/user/blocks/event-query.md
---

# Browse events

People look through the site's events: upcoming events soonest first, including those under way, or past events most recent first; on a topic's page; and in the admin Events list with its Upcoming and Past views.
