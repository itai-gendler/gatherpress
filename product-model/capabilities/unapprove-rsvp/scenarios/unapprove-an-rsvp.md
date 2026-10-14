---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Unapprove for an RSVP
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
- text: The Product sets the RSVP back to pending
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

# Unapprove an RSVP

## Trigger

An approved RSVP should not stand for now.

## Outcome

The RSVP is pending, off the attendee list and out of the counts.
