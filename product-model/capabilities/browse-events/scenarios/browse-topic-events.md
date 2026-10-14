---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens a topic page
  kind: actor
  actor: visitor
  entities:
  - entity: topic
    effect: reads
    facts:
    - Name
    - Description
  contexts:
    web:
      place: web::public::topic-archive
- text: The Product lists the events under the topic
  kind: product
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - End
    - Venue
  - entity: topic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::topic-archive
---

# Browse the events of a topic

## Trigger

A visitor is interested in one kind of event.

## Outcome

The visitor sees the topic and its events.
