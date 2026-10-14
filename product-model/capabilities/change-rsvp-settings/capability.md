---
availability:
- place: web::administration
domain: settings
references:
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-rsvp.php#Rsvp
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-setup.php#Setup.maybe_disable_rsvp
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
---

# Change RSVP settings

An administrator sets the RSVP mode for the whole site, whether visitors without an account may RSVP, the capacity, guest limit and anonymous listing new events start with, and the automatic cleanup of unconfirmed RSVPs.
