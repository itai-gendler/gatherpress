---
type: web
actors:
- visitor
- subscriber
- author
- editor
- administrator
entryPoints:
- web: /event/<event-slug>/
- web: /event/
- web: /venue/<venue-slug>/
- web: /topic/<topic-slug>/
- web: /wp-admin/edit.php?post_type=gatherpress_event
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-setup.php
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-setup.php
- kind: code
  role: implementation
  target: includes/core/classes/class-settings.php
---

# GatherPress website

The WordPress site GatherPress runs on: its public event, venue and topic pages, and the WordPress admin where people sign in to manage events, venues, topics, RSVPs, their profile and the GatherPress settings.
