---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor chooses iCal under Add to Calendar on the event page
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product hands over a calendar file of the event
  kind: product
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Description
    - Start
    - End
    - Timezone
    - Venue
  contexts:
    web:
      place: web::public::event-page
---

# Download an event to a calendar

## Trigger

A visitor wants the event in their calendar application.

## Outcome

The visitor has a calendar file of the event with its title, times, description and venue.
