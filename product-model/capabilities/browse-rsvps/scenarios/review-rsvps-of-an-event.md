---
kind: primary
routes:
  web: Web
steps:
- text: The Editor opens RSVPs and filters by an event and the Attending response
  kind: actor
  actor: editor
  entities:
  - entity: event
    effect: reads
    facts:
    - Title
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::rsvps
- text: The Product lists the RSVPs of the event with their details
  kind: product
  actor: editor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
    - Email
    - Guests
    - Type
    - Approval
    - Checked in
    - Submitted at
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::rsvps
---

# Review the RSVPs of an event

## Trigger

An editor prepares for an event.

## Outcome

The editor sees each RSVP of the event with its attendee, email, response, type, approval, check-in and date.
