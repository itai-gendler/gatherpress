---
kind: alternative
routes:
  feed: Calendar feed
steps:
- text: The Calendar app requests the feed of a topic
  kind: actor
  actor: calendar-app
  entities:
  - entity: topic
    effect: reads
    facts:
    - Name
  contexts:
    feed:
      place: calendar-feeds
- text: The Product returns the upcoming events under the topic
  kind: product
  actor: calendar-app
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Description
    - Start
    - End
    - Timezone
    - Venue
  - entity: topic
    effect: reads
    facts: []
  contexts:
    feed:
      place: calendar-feeds
---

# Refresh a topic feed

## Trigger

A calendar app subscribed to one topic's feed checks it.

## Outcome

The calendar shows the upcoming events under that topic.
