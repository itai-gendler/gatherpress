---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes the date and time formats and the archive pages and saves the tab
  kind: actor
  actor: administrator
  entities:
  - entity: site-settings
    effect: reads
    facts:
    - Date format
    - Time format
    - Past events page
  contexts:
    web:
      place: web::administration::events-settings
- text: The Product saves the events settings
  kind: product
  actor: administrator
  entities:
  - entity: site-settings
    effect: changes
    facts:
    - Date format
    - Time format
    - Show timezone
    - Event date as publish date
    - Event archive
    - Upcoming events page
    - Past events page
    - Events permalink
    - Topics permalink
  - entity: event
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::events-settings
---

# Set date display and the events archive

## Trigger

The site should show dates in the community's format and list past events on its own page.

## Outcome

Event dates use the new formats and the chosen page lists past events.

## Edge cases

- Changing the event or topic permalink changes the addresses of their pages and feeds.
