---
kind: alternative
routes:
  web: Web
steps:
- text: The Author marks the event as online and pastes the joining link
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product saves the event as online with its link
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - Online event
    - Online event link
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Make an event online

## Trigger

The event can be joined from a video call or livestream.

## Outcome

The event is an online event with a joining link, which only its attendees will see.

## Edge cases

- An event with a venue and an online link is a hybrid event and shows both.
