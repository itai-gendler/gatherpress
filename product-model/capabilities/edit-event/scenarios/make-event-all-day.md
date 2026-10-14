---
kind: alternative
routes:
  web: Web
steps:
- text: The Author turns on All day and picks the first and last day
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product stores the event from the start of the first day to the end of the last and stops appending its timezone
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - All day
    - Start
    - End
    - Append time zone
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Make an event all day

## Trigger

The event runs whole days rather than set hours.

## Outcome

The event runs from the start of its first day to the end of its last, shows its date without a time and no longer appends its timezone.

## Edge cases

- Turning All day off while the editor is still open restores the times the event had before.
- Append time zone set to Always stays Always when All day is turned on.
