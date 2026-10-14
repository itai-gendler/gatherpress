---
kind: primary
routes:
  web: Web
steps:
- text: The Author picks Attending and adds the member by username in the attendee manager of the event
  kind: actor
  actor: author
  entities:
  - entity: account
    effect: reads
    facts:
    - Display name
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product records the RSVP of the member as attending
  kind: product
  actor: author
  entities:
  - entity: event
    effect: reads
    facts:
    - Capacity
  - entity: rsvp
    effect: creates
    to: Attending
    facts:
    - Name
    - Type
    - Approval
    - Submitted at
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Add a member as attending

## Trigger

A member told the organizer in person that they are coming.

## Outcome

The member is attending the event, or on its waiting list when it is full.
