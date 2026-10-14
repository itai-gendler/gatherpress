---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor fills in name, email, the questions, guests and event email choice on the RSVP form and submits it
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - RSVP form questions
    - Guest limit
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product records an attending RSVP awaiting confirmation with the answers given
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
  contexts:
    web:
      place: web::public::event-page
- text: The Product emails the Visitor a link to confirm the RSVP, with the event title, date and venue
  kind: product
  actor: visitor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Email
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - Venue
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
---

# Send an RSVP with a name and email

## Trigger

A visitor without an account wants to come to an event.

## Outcome

An unconfirmed RSVP is recorded and the visitor has an email with a link to confirm it.

## Decision points

### Whose RSVP is it?

Does the email address belong to an account on the site?

- Yes → the RSVP is recorded for that account, under its display name
- No → the RSVP is recorded under the name and email given
