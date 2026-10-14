---
kind: primary
routes:
  web: Web
steps:
- text: The Author unticks a topic of the event
  kind: actor
  actor: author
  entities:
  - entity: topic
    effect: reads
    facts:
    - Name
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product removes the topic from the event
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - Topics
  - entity: topic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Take an event out of a topic

## Trigger

The event was grouped under the wrong topic.

## Outcome

The event no longer appears on that topic's page or feed.
