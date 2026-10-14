---
kind: alternative
routes:
  web: Web
steps:
- text: The Editor looks at the attendee list on the event page
  kind: actor
  actor: editor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-page
- text: The Product lists every approved RSVP by name, including those listed as anonymous
  kind: product
  actor: editor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
    - Guests
    - Anonymous
  contexts:
    web:
      place: web::signed-in::event-page
---

# See anonymous attendees by name

## Trigger

An editor checks the attendee list of an event.

## Outcome

The editor sees every attendee by name, anonymous ones included.
