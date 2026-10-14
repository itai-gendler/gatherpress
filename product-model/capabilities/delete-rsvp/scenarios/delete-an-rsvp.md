---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Delete for an RSVP
  kind: actor
  actor: editor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::rsvps
- text: The Product deletes the RSVP
  kind: product
  actor: editor
  entities:
  - entity: rsvp
    effect: removes
    from: Attending
  contexts:
    web:
      place: web::signed-in::rsvps
---

# Delete an RSVP

## Trigger

An RSVP should not exist at all.

## Outcome

The RSVP is gone from the event.
