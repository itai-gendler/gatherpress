---
kind: alternative
routes:
  web: Web
steps:
- text: The Author raises the event capacity and saves
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product saves the new capacity of the event
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - Capacity
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product moves the earliest RSVPs on the waiting list to attending while places remain
  kind: product
  actor: author
  entities:
  - entity: event
    effect: reads
    facts:
    - Capacity
  - entity: rsvp
    effect: changes
    from: Waiting list
    to: Attending
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Raise an event's capacity

## Trigger

More room becomes available at a full event.

## Outcome

The event has the larger capacity and the people who waited longest are now attending, as many as fit.

## Edge cases

- Setting the capacity to 0 removes the limit and moves everyone on the waiting list to attending.
