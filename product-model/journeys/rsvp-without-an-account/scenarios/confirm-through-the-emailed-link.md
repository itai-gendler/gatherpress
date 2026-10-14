---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Visitor fills in the RSVP form of the event and submits it
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - RSVP form questions
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product records the RSVP awaiting confirmation and emails a confirmation link
  kind: product
  actor: visitor
  entities:
  - entity: rsvp
    effect: creates
    to: Attending
    facts:
    - Name
    - Email
    - Type
    - Guests
    - Anonymous
    - Answers
    - Event updates
    - Approval
    - Submitted at
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - Venue
  contexts:
    web:
      place: web::public::event-page
  capability: rsvp-without-account
- text: The Visitor follows the Confirm My RSVP link in the email
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
  capability: confirm-rsvp
---

# Confirm through the emailed link

## Trigger

A visitor without an account wants to come to an event that accepts Open RSVP.

## Outcome

The visitor is an approved attendee, listed on the event and counted toward its capacity.
