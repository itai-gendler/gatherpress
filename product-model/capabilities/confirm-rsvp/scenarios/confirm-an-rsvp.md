---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor follows the Confirm My RSVP link from the email
  kind: actor
  actor: visitor
  entities:
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product approves the RSVP and shows the event page with it
  kind: product
  actor: visitor
  entities:
  - entity: rsvp
    effect: changes
    facts:
    - Approval
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
---

# Confirm an RSVP from the email

## Trigger

The visitor opens the confirmation email and follows its link.

## Outcome

The RSVP is approved, appears in the attendee list and counts toward the event; the event page shows the visitor's response.
