---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator removes the account from Organizers on the Roles tab and saves
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
- text: The Product stops listing the account as an Organizer
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

# Stop listing someone as an organizer

## Trigger

A person no longer organizes.

## Outcome

The person appears as Member in attendee lists.
