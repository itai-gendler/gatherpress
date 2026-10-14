---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Add New and enters a title and description
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product creates the event as a draft dated tomorrow at 6 pm for two hours, with RSVP defaults from the site settings
  kind: product
  actor: author
  entities:
  - entity: site-settings
    effect: reads
    facts:
    - RSVP mode
    - Default capacity
    - Default guest limit
    - Anonymous RSVP default
  - entity: event
    effect: creates
    to: Draft
    facts:
    - Title
    - Description
    - Start
    - End
    - Timezone
    - RSVP enabled
    - Open RSVP
    - Anonymous RSVP
    - Capacity
    - Guest limit
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Start a new event

## Trigger

An organizer is planning a gathering.

## Outcome

A draft event exists, dated the next day at 6 pm for two hours in the site timezone, taking RSVPs as the site's RSVP mode and defaults say.

## Decision points

### Does the new event take RSVPs?

Which RSVP mode is the site in?

- All events or Per event (default on) → the event takes RSVPs
- Per event (default off) → the event starts with RSVPs turned off
- Disabled → the event has no RSVP settings at all
