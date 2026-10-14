---
kind: primary
routes:
  web: Web
steps:
- text: The Author ticks a topic for the event
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
- text: The Product adds the topic to the event
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

# Put an event under a topic

## Trigger

The event belongs with others of its kind.

## Outcome

The event appears on the topic page and in the topic feed.
