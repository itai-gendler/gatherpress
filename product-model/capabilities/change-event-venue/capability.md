---
availability:
- place: web::signed-in
domain: events
references:
- kind: code
  role: implementation
  target: src/components/VenueSelector.js
- kind: code
  role: implementation
  target: includes/core/classes/class-shadow-source.php#Shadow_Source
- kind: doc
  role: intent
  target: docs/user/creating-and-managing-events.md
---

# Change event venue

An organizer chooses which published venue an event is held at, or leaves it without one, from the Venue Selector of the event.
