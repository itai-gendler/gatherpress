---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber opens the venue page
  kind: actor
  actor: subscriber
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::venue-page
- text: The Product shows the venue name, address, phone, website and map
  kind: product
  actor: subscriber
  entities:
  - entity: venue
    effect: reads
    facts:
    - Name
    - Address
    - Phone
    - Website
    - Latitude
    - Longitude
  contexts:
    web:
      place: web::signed-in::venue-page
---

# View a venue while signed in

## Trigger

A member checks where the next meetup is held.

## Outcome

The member sees the venue's details and its map.
