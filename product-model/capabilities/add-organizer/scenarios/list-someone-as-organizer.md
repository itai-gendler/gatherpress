---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator selects the account under Organizers on the Roles tab and saves
  kind: actor
  actor: administrator
  entities:
  - entity: account
    effect: reads
    facts:
    - Display name
  contexts:
    web:
      place: web::administration::roles-settings
- text: The Product lists the account as an Organizer
  kind: product
  actor: administrator
  entities:
  - entity: account
    effect: changes
    facts:
    - Organizer
  contexts:
    web:
      place: web::administration::roles-settings
---

# List someone as an organizer

## Trigger

A member helps run the community's events.

## Outcome

The person appears as Organizer in attendee lists.
