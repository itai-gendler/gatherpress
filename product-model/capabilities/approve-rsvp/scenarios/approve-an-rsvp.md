---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Approve for an RSVP
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
- text: The Product approves the RSVP
  kind: product
  actor: editor
  entities:
  - entity: rsvp
    effect: changes
    facts:
    - Approval
  contexts:
    web:
      place: web::signed-in::rsvps
---

# Approve an RSVP

## Trigger

An RSVP sent without an account is still unconfirmed.

## Outcome

The RSVP is approved, counted and listed on the event.
