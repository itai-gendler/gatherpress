---
kind: primary
routes:
  web: Web
steps:
- text: The Subscriber picks a timezone and 24-hour time, unticks the updates choice in their profile and saves
  kind: actor
  actor: subscriber
  entities:
  - entity: account
    effect: reads
    facts:
    - Event updates
    - Time format
    - Timezone
  contexts:
    web:
      place: web::signed-in::profile
- text: The Product saves the preferences of the account
  kind: product
  actor: subscriber
  entities:
  - entity: account
    effect: changes
    facts:
    - Event updates
    - Time format
    - Timezone
  contexts:
    web:
      place: web::signed-in::profile
---

# Set time display and event email preference

## Trigger

A member lives in another timezone and does not want event emails.

## Outcome

Event times on the site are shown to the member in their timezone and format, and organizer emails skip them.
