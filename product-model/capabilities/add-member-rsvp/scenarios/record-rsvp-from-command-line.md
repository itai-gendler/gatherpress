---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs wp gatherpress event rsvp with the event, the user, a status, guests and anonymity
  kind: actor
  actor: operator
  entities:
  - entity: event
    effect: reads
    facts: []
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    cli:
      place: wp-cli
- text: The Product records the RSVP for that user and reports the status it stored
  kind: product
  actor: operator
  entities:
  - entity: event
    effect: reads
    facts:
    - Capacity
    - Guest limit
    - Anonymous RSVP
  - entity: rsvp
    effect: creates
    to: Attending
    facts:
    - Name
    - Type
    - Guests
    - Anonymous
    - Approval
    - Submitted at
  contexts:
    cli:
      place: wp-cli
---

# Record an RSVP from the command line

## Trigger

An operator imports responses gathered elsewhere.

## Outcome

The member has the RSVP given, with guests and anonymity as the event allows, and the command reports the status recorded.

## Edge cases

- A post that does not take RSVPs is refused with an error naming it.
