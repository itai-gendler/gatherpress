---
appliesTo:
- type: capability
  id: rsvp-to-event
- type: capability
  id: rsvp-without-account
- type: capability
  id: view-attendees
- type: capability
  id: change-rsvp-settings
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php#Rsvp.is_enabled
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-setup.php#Setup.maybe_disable_rsvp
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
---

# An event takes RSVPs only as the RSVP mode allows

All events: every event takes RSVPs. Per event (default on or off): each event follows its own RSVP switch, new events starting on or off. Disabled: no event takes RSVPs and the RSVP blocks, the RSVPs page and the RSVP settings of events are gone.
