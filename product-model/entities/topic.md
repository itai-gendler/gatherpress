---
domain: topics
relations:
- entity: event
  verb: groups
  cardinality: many-to-many
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-topic.php
- kind: doc
  role: intent
  target: docs/user/topics.md
---

# Topic

A category events are grouped under, which can sit inside a parent topic and has its own page and feed.

## Information kept

- **Name** — the topic's name
- **Slug** — the name in its page and feed addresses
- **Parent topic** — the topic it sits under, if any
- **Description** — what the topic covers
