---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens the event page from the emailed link and chooses Not Attending
  kind: actor
  actor: visitor
  entities:
  - entity: rsvp
    effect: reads
    facts:
    - Name
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::event-page
- text: The Product records their RSVP as not attending
  kind: product
  actor: visitor
  entities:
  - entity: rsvp
    effect: changes
    from: Attending
    to: Not attending
    facts:
    - Guests
  contexts:
    web:
      place: web::public::event-page
---

# Change an RSVP from the emailed link

## Trigger

A person who RSVPed without an account opens the event from the link in their confirmation email and their plans changed.

## Outcome

Their RSVP says not attending.
