---
appliesTo:
- type: capability
  id: change-event-venue
- type: capability
  id: publish-venue
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-shadow-source.php#Shadow_Source.add_term
---

# Only published venues can be chosen for an event

A venue enters the Venue Selector when it is published.
