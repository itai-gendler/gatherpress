---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the event page
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product shows the event title, description, date and time in its timezone, and its venue with address and map
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
    - All day
    - Append time zone
    - Venue
  - entity: venue
    effect: reads
    facts:
    - Name
    - Address
    - Latitude
    - Longitude
  contexts:
    web:
      place: web::public::event-page
---

# View an event

## Trigger

A visitor follows a link to an event.

## Outcome

The visitor sees when and where the event is.

## Edge cases

- An all-day event shows the same dates to every visitor whatever their timezone.
