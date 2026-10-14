---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens All Events and picks the Upcoming view
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::events-list
- text: The Product lists the events with their date and time, venue, topics and RSVP counts
  kind: product
  actor: author
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
    - Start
    - End
    - Timezone
    - Venue
    - Topics
  - entity: rsvp
    effect: reads
    facts:
    - Approval
  - entity: venue
    effect: reads
    facts: []
  - entity: topic
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::events-list
---

# Browse events in the admin

## Trigger

An organizer reviews what is planned.

## Outcome

The organizer sees every event with its date and time, venue and RSVP count, unapproved RSVPs flagged, in the Upcoming, Past or All view.
