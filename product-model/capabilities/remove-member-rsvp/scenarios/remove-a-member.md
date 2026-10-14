---
kind: primary
routes:
  web: Web
steps:
- text: The Author removes the member from the attendee manager of the event
  kind: actor
  actor: author
  entities:
  - entity: rsvp
    as: theirs
    effect: reads
    facts:
    - Name
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product deletes the RSVP of the member
  kind: product
  actor: author
  entities:
  - entity: rsvp
    as: theirs
    effect: removes
    from: Attending
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Remove a member from an event

## Trigger

A member was added by mistake.

## Outcome

The member has no RSVP for the event.

## Edge cases

- The waiting list moves up when the event is next saved or someone next responds, not at the removal itself.
