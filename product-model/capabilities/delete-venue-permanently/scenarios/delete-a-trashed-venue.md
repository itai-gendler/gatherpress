---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Delete Permanently for the trashed venue
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::venues-list
- text: The Product deletes the venue and clears it from the events held there
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: removes
    from: Trashed
  - entity: event
    effect: changes
    facts:
    - Venue
  contexts:
    web:
      place: web::signed-in::venues-list
---

# Delete a trashed venue for good

## Trigger

A trashed venue will not be needed again.

## Outcome

The venue is gone and the events that were held there show no venue.
