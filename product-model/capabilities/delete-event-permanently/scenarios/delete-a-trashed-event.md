---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Delete Permanently for the trashed event
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::events-list
- text: The Product deletes the event and its RSVPs
  kind: product
  actor: author
  entities:
  - entity: event
    effect: removes
    from: Trashed
  - entity: rsvp
    effect: removes
    from: Attending
    with: event
  contexts:
    web:
      place: web::signed-in::events-list
---

# Delete a trashed event for good

## Trigger

A trashed event will not be needed again.

## Outcome

The event and its RSVPs are gone and it no longer appears in any list.
