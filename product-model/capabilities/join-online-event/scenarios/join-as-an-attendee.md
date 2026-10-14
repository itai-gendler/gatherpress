---
kind: primary
routes:
  web: Web
steps:
- text: The Subscriber who is attending opens the event page
  kind: actor
  actor: subscriber
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product shows the online event link
  kind: product
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Online event
    - Online event link
  contexts:
    web:
      place: web::signed-in::event-page
---

# Join an online event as an attendee

## Trigger

An attending member wants to join the online event.

## Outcome

The member sees the joining link.

## Edge cases

- Once the event has ended the link is no longer shown, even to attendees.
