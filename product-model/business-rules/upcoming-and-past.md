---
appliesTo:
- type: capability
  id: browse-events
- type: capability
  id: subscribe-to-calendar-feed
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-query.php#Query.adjust_event_sql
- kind: code
  role: implementation
  target: includes/core/classes/calendar/class-setup.php#Setup.get_ical_list
---

# An event is upcoming until it ends and past once it has ended

Upcoming lists and the calendar feeds include events under way; past lists hold only events that have ended. An event with no date yet is in neither.
