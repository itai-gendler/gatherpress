---
kind: alternative
routes:
  web: Web
steps:
- text: The Author changes RSVP, Open RSVP, anonymous listing and the guest limit in the RSVP settings of the event
  kind: actor
  actor: author
  entities:
  - entity: event
    effect: reads
    facts: []
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
- text: The Product saves the RSVP settings of the event
  kind: product
  actor: author
  entities:
  - entity: event
    effect: changes
    facts:
    - RSVP enabled
    - Open RSVP
    - Anonymous RSVP
    - Guest limit
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::event-editor
---

# Change an event's RSVP settings

## Trigger

The organizer wants this event to take RSVPs differently from the site defaults.

## Outcome

The event takes RSVPs, accepts responses without an account, allows anonymous listing and allows guests as now set.

## Decision points

### Is there an Enable RSVP control?

Which RSVP mode is the site in?

- Per event (default on) or Per event (default off) → the organizer also turns RSVP on or off for this event
- All events → every event takes RSVPs and only the other settings change
