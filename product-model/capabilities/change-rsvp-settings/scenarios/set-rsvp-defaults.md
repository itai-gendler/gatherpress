---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks the mode that leaves the choice to each one, off by default, sets the default capacity and guest limit and saves the tab
  kind: actor
  actor: administrator
  entities:
  - entity: site-settings
    effect: reads
    facts:
    - RSVP mode
  contexts:
    web:
      place: web::administration::rsvp-settings
- text: The Product saves the RSVP settings
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: changes
    facts:
    - RSVP mode
    - Open RSVP
    - Default capacity
    - Default guest limit
    - Anonymous RSVP default
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::rsvp-settings
---

# Set RSVP defaults

## Trigger

The site wants each event to decide whether it takes RSVPs, starting with them off.

## Outcome

Events get their own RSVP switch, starting off for new events, with the new capacity and guest defaults.
