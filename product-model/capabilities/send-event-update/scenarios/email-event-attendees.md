---
kind: primary
routes:
  web: Web
steps:
- text: The Author composes a message for the event, picks Attending as recipients and sends it
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product emails each attending RSVP that has not turned off event updates, with the message and the event details
  kind: product
  actor: author
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Email
    - Event updates
  - entity: account
    effect: reads
    facts:
    - Email
    - Event updates
  - entity: event
    effect: reads
    facts:
    - Title
    - Featured image
    - Start
    - End
    - Venue
    - RSVP enabled
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Email the attendees of an event

## Trigger

Something about the event changed and the people coming should know.

## Outcome

Every attending person who has not turned off event emails receives the message with the event details.

## Decision points

### Does a recipient get the email?

Has the recipient turned off event updates?

- A member with Event updates off in their profile, or a person without an account who declined updates on the RSVP form → skipped
- Anyone else → emailed
