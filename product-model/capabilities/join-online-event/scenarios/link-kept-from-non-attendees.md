---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens the event page of an online event
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product shows that the event is online and that the link is for attendees
  kind: product
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - Online event
  contexts:
    web:
      place: web::public::event-page
---

# The link is kept from people not attending

## Trigger

A visitor who has not RSVPed opens an online event.

## Outcome

The visitor sees that it is an online event and that the link is for attendees.
