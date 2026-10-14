---
kind: primary
routes:
  web: Web
steps:
- text: The Editor enters a name, slug, parent and description under Topics
  kind: actor
  actor: editor
  entities:
  - entity: topic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::topics
- text: The Product creates the topic
  kind: product
  actor: editor
  entities:
  - entity: topic
    effect: creates
    facts:
    - Name
    - Slug
    - Parent topic
    - Description
  contexts:
    web:
      place: web::signed-in::topics
---

# Add a topic

## Trigger

Events of a new kind are planned.

## Outcome

The topic exists and can be ticked on events.
