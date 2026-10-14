---
kind: alternative
routes:
  web: Web
steps:
- text: The Author adds a field to the RSVP Form with its type, name, label and whether it is required
  kind: actor
  actor: author
  entities:
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product saves the RSVP form questions of the event when the event is saved
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - RSVP form questions
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Add a question to the RSVP form

## Trigger

The organizer needs to know more from people who RSVP without an account, such as dietary needs.

## Outcome

The RSVP form of the event asks the new question, and answers to it are checked and kept with each RSVP.
