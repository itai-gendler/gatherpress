---
kind: primary
routes:
  web: Web
steps:
- text: The Editor deletes the topic
  kind: actor
  actor: editor
  entities:
  - entity: topic
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::topics
- text: The Product deletes the topic and takes it off its events
  kind: product
  actor: editor
  entities:
  - entity: topic
    effect: removes
  - entity: event
    effect: changes
    facts:
    - Topics
  contexts:
    web:
      place: web::signed-in::topics
---

# Delete a topic

## Trigger

A topic is no longer used.

## Outcome

The topic and its page are gone; its events remain under their other topics.
