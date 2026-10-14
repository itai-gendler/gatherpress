---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber chooses Edit RSVP on the event page and then Not Attending
  kind: actor
  actor: subscriber
  entities:
  - entity: rsvp
    as: mine
    effect: reads
    facts:
    - Guests
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product records the RSVP as not attending, without guests
  kind: product
  actor: subscriber
  entities:
  - entity: rsvp
    as: mine
    effect: changes
    from: Attending
    to: Not attending
    facts:
    - Guests
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product moves the earliest RSVP on the waiting list to attending
  kind: product
  actor: subscriber
  entities:
  - entity: rsvp
    as: next
    effect: changes
    from: Waiting list
    to: Attending
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
---

# Stop attending an event

## Trigger

A member who said yes can no longer come.

## Outcome

The member is not attending, and the person who waited longest is now attending if there is room.
