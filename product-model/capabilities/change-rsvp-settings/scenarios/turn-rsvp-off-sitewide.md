---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator picks Disabled as the mode and saves the tab
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::rsvp-settings
- text: The Product turns RSVP off for every event
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: changes
    facts:
    - RSVP mode
  - entity: event
    effect: reads
    facts: []
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::rsvp-settings
---

# Turn RSVP off for the whole site

## Trigger

The site only publishes events and does not take responses.

## Outcome

No event takes RSVPs: the RSVP blocks, the RSVPs page and the RSVP settings of events are gone.
