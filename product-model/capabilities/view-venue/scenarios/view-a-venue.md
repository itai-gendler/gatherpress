---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the venue page
  kind: actor
  actor: visitor
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::venue-page
- text: The Product shows the venue name, address, phone, website, description and map
  kind: product
  actor: visitor
  entities:
  - entity: venue
    effect: reads
    facts:
    - Name
    - Description
    - Address
    - Phone
    - Website
    - Latitude
    - Longitude
  contexts:
    web:
      place: web::public::venue-page
---

# View a venue

## Trigger

A visitor wants to know where a venue is.

## Outcome

The visitor sees the venue's details and its map.

## Edge cases

- The map is drawn with the mapping platform the site chose, as a live map or a still image as the organizer set it.
