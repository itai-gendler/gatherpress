---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses Spam for an RSVP
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
- text: The Product marks the RSVP as spam
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

# Mark an RSVP as spam

## Trigger

An RSVP was not sent by a real person.

## Outcome

The RSVP is spam, off the attendee list and out of the counts.
