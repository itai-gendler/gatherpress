---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: event
  verb: writes
  cardinality: one-to-many
- entity: venue
  verb: writes
  cardinality: one-to-many
---

# Author

A signed-in organizer who creates and publishes their own events and venues and manages the attendees of events they wrote.
