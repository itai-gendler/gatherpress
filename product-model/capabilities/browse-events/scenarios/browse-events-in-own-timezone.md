---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber opens the events archive
  kind: actor
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::events-archive
- text: The Product lists the events with their times in the timezone and time format of the account
  kind: product
  actor: subscriber
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - End
    - Venue
  - entity: account
    effect: reads
    facts:
    - Timezone
    - Time format
  contexts:
    web:
      place: web::signed-in::events-archive
- text: The Subscriber opens a topic page from an event
  kind: actor
  actor: subscriber
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
      place: web::signed-in::topic-archive
- text: The Product lists the events under the topic
  kind: product
  actor: subscriber
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
      place: web::signed-in::topic-archive
---

# Browse events in one's own timezone

## Trigger

A member who set a timezone in their profile looks at the events archive.

## Outcome

Event times are shown in the member's timezone and time format.
