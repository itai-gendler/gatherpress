---
kind: primary
routes:
  web: Web
steps:
- text: The Subscriber chooses RSVP on the event page, sets the number of guests and confirms Attending
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Guest limit
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product records the RSVP as attending and approved, with guests up to the guest limit of the event
  kind: product
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Capacity
    - Guest limit
    - Anonymous RSVP
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

# Attend an event

## Trigger

A member decides to go to an event.

## Outcome

The member is attending with their guests, and the RSVP block shows them as attending.

## Edge cases

- Asking for more guests than the event allows records the RSVP with the allowed number, without an error.
