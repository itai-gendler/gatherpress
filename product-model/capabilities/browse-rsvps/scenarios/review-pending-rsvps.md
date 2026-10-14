---
kind: alternative
routes:
  web: Web
steps:
- text: The Editor opens RSVPs and picks the Pending view
  kind: actor
  actor: editor
  entities:
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::rsvps
- text: The Product lists the RSVPs awaiting approval
  kind: product
  actor: editor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
    - Email
    - Approval
    - Submitted at
  contexts:
    web:
      place: web::signed-in::rsvps
---

# Review RSVPs awaiting approval

## Trigger

Unconfirmed RSVPs are flagged on the events list.

## Outcome

The editor sees only the RSVPs awaiting approval.
