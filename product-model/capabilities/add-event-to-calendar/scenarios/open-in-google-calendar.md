---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber chooses Google Calendar under Add to Calendar on the event page
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product sends the Subscriber to Google Calendar with the event prefilled
  kind: product
  actor: subscriber
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
      place: web::signed-in::event-page
---

# Add an event to Google Calendar

## Trigger

A member keeps their calendar in Google Calendar.

## Outcome

Google Calendar opens with the event prefilled.
