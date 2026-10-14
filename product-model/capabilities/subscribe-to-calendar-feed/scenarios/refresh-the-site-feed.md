---
kind: primary
routes:
  feed: Calendar feed
steps:
- text: The Calendar app requests the site feed
  kind: actor
  actor: calendar-app
  entities: []
  contexts:
    feed:
      place: calendar-feeds
- text: The Product returns the published events that have not ended, with title, description, times and venue
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

# Refresh the site feed

## Trigger

A calendar app subscribed to the site feed checks it.

## Outcome

The calendar shows every upcoming published event with its current details.

## Edge cases

- An event drops out of the feed once it has ended.
