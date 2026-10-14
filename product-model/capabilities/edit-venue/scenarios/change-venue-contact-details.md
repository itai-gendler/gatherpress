---
kind: alternative
routes:
  web: Web
steps:
- text: The Author changes the phone and website of the venue and saves
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::venue-editor
- text: The Product saves the phone and website
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: changes
    facts:
    - Phone
    - Website
  contexts:
    web:
      place: web::signed-in::venue-editor
---

# Change a venue's phone and website

## Trigger

The venue's contact details changed.

## Outcome

The venue page and the events held there show the new phone and website.
