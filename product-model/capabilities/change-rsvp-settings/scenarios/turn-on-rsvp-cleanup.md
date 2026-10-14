---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator turns cleanup on, picks a frequency and an interval and saves the tab
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::rsvp-settings
- text: The Product saves the cleanup settings and schedules the next cleanup
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: changes
    facts:
    - RSVP cleanup
    - Cleanup frequency
    - Cleanup interval
  contexts:
    web:
      place: web::administration::rsvp-settings
---

# Turn on cleanup of unconfirmed RSVPs

## Trigger

Unconfirmed RSVPs pile up.

## Outcome

Unconfirmed RSVPs are removed on the chosen schedule, starting one interval from now.
