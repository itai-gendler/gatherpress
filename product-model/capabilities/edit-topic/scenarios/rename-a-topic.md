---
kind: primary
routes:
  web: Web
steps:
- text: The Editor changes the name and slug of the topic
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
- text: The Product saves the topic
  kind: product
  actor: editor
  entities:
  - entity: topic
    effect: changes
    facts:
    - Name
    - Slug
  contexts:
    web:
      place: web::signed-in::topics
---

# Rename a topic

## Trigger

A topic's name no longer fits.

## Outcome

The topic has its new name and slug, and its page and feed addresses use the new slug.
