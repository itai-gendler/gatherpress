---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber ticks List me as anonymous and confirms Attending on the event page
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Anonymous RSVP
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product records the RSVP as attending and anonymous
  kind: product
  actor: subscriber
  entities:
  - entity: rsvp
    effect: creates
    to: Attending
    facts:
    - Name
    - Type
    - Guests
    - Anonymous
    - Approval
    - Submitted at
  contexts:
    web:
      place: web::signed-in::event-page
---

# RSVP anonymously

## Trigger

A member wants to come without being named in the public attendee list.

## Outcome

The member is attending and listed as Anonymous to everyone except editors and administrators.

## Edge cases

- When the event does not allow anonymous RSVPs the choice is not offered and the RSVP is recorded as named.
