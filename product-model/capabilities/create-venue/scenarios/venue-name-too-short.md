---
kind: validation
routes:
  web: Web
steps:
- text: The Author enters a venue name shorter than two characters in the Venue block
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product refuses the name and creates no venue
  kind: condition
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# A venue name is too short

## Trigger

The organizer tries to add a venue from an event with an empty or one-letter name.

## Outcome

No venue is created and the form asks for a name of at least two characters.
