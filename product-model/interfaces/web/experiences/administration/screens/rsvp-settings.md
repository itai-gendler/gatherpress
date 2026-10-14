---
entities:
- entity: site-settings
  shows: &id001
  - RSVP mode
  - Open RSVP
  - Default capacity
  - Default guest limit
  - Anonymous RSVP default
  - RSVP cleanup
  - Cleanup frequency
  - Cleanup interval
  collects: *id001
references:
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-rsvp.php
---

# RSVP settings

The RSVP tab: the RSVP mode, Open RSVP, defaults for new events and the cleanup of unconfirmed RSVPs.
