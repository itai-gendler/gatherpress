---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: rsvp
  verb: sends
  cardinality: one-to-many
---

# Subscriber

A signed-in member of the site with no editing rights: the least privileged role, standing for any signed-in person when they RSVP to events, read the online link of an event they attend and keep their own profile. GatherPress calls such people members.
