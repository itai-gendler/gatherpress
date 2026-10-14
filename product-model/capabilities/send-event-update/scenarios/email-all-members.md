---
kind: alternative
routes:
  web: Web
steps:
- text: The Author composes a message for the event, picks All Members and sends it
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
- text: The Product emails every account on the site that has not turned off event updates
  kind: product
  actor: author
  entities:
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

# Email every member about an event

## Trigger

The organizer wants the whole community to hear about the event.

## Outcome

Every user of the site who has not turned off event updates receives the message with the event details and an RSVP Now link.

## Edge cases

- Once the event has ended the email carries no RSVP Now link.
