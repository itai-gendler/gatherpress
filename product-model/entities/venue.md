---
domain: venues
relations:
- entity: event
  verb: hosts
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: includes/core/classes/venue/class-venue.php
- kind: code
  role: implementation
  target: includes/core/classes/venue/class-meta.php
- kind: doc
  role: intent
  target: docs/user/venues.md
---

# Venue

A physical place events are held at, kept once and reused by every event held there.

## Information kept

- **Name** — the venue's name
- **Description** — anything else about the place, written in the editor
- **Address** — its full address
- **Structured address** — house number, street, city, county, state, postcode, country and country code, looked up from the address
- **Latitude** — where it is on the map
- **Longitude** — where it is on the map
- **Phone** — its phone number
- **Website** — its website

## States

### Draft

Being prepared; it cannot be chosen for an event yet.

### Published

Live on the site and available to choose for events.

### Trashed

In the trash and restorable until deleted permanently.
