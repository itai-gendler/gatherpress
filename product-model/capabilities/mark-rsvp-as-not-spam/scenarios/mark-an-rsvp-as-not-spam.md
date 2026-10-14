---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Not Spam for an RSVP
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

# Mark an RSVP as not spam

## Trigger

A real RSVP was marked as spam.

## Outcome

The RSVP is approved again.
