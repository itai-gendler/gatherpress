---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber opens the event page
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product shows the event times in the timezone and time format of the account
  kind: product
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - End
    - Timezone
  - entity: account
    effect: reads
    facts:
    - Timezone
    - Time format
  contexts:
    web:
      place: web::signed-in::event-page
---

# View an event in one's own timezone

## Trigger

A member with a timezone and time format in their profile opens an event.

## Outcome

The member sees the event times converted to their timezone and format.
