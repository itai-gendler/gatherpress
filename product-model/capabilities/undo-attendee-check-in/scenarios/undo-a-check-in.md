---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Not Checked In for an RSVP
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
- text: The Product marks the RSVP as not checked in
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

# Undo a check-in

## Trigger

An attendee was checked in by mistake.

## Outcome

The RSVP shows as not checked in.
