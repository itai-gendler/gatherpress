---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber chooses RSVP on the event page and confirms Attending
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts: []
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The event has no room for them
  kind: condition
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Capacity
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product records the RSVP on the waiting list without guests
  kind: product
  actor: subscriber
  entities:
  - entity: rsvp
    effect: creates
    to: Waiting list
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

# Join the waiting list of a full event

## Trigger

A member RSVPs to an event whose capacity is taken.

## Outcome

The member is on the waiting list, without guests, behind everyone who joined it earlier.
