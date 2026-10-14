---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Check in for an RSVP
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
- text: The Product marks the RSVP as checked in
  kind: product
  actor: editor
  entities:
  - entity: rsvp
    effect: changes
    facts:
    - Checked in
  contexts:
    web:
      place: web::signed-in::rsvps
---

# Check in an attendee

## Trigger

An attendee arrives at the event.

## Outcome

The RSVP shows as checked in.

## Edge cases

- Only approved RSVPs offer Check in.
