---
kind: alternative
routes:
  feed: Calendar feed
steps:
- text: The Calendar app requests the feed of a venue
  kind: actor
  actor: calendar-app
  entities:
  - entity: venue
    effect: reads
    facts:
    - Name
  contexts:
    feed:
      place: calendar-feeds
- text: The Product returns the upcoming events held at the venue
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
  - entity: venue
    effect: reads
    facts: []
  contexts:
    feed:
      place: calendar-feeds
---

# Refresh a venue feed

## Trigger

A calendar app subscribed to one venue's feed checks it.

## Outcome

The calendar shows the upcoming events at that venue.
