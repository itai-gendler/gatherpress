---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor looks at the attendee list on the event page and picks Attending
  kind: actor
  actor: visitor
  entities:
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product lists the approved RSVPs that are attending with name, avatar, role and guests
  kind: product
  actor: visitor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
    - Guests
    - Anonymous
  - entity: account
    effect: reads
    facts:
    - Organizer
  contexts:
    web:
      place: web::public::event-page
---

# See who is coming

## Trigger

A visitor wonders who else will be at the event.

## Outcome

The visitor sees the attending people, organizers first, with their guests; anonymous attendees appear as Anonymous.
