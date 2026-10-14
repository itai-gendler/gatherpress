---
kind: unattended
routes:
  web: Web
steps:
- text: RSVP cleanup is on and its interval has passed
  kind: condition
  unattended: true
  entities:
  - entity: site-settings
    effect: reads
    facts:
    - RSVP cleanup
    - Cleanup frequency
    - Cleanup interval
  - entity: rsvp
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::rsvps
- text: The Product deletes pending RSVPs sent more than a day ago
  kind: product
  entities:
  - entity: rsvp
    effect: removes
    from: Attending
  contexts:
    web:
      place: web::signed-in::rsvps
---

# Clean up unconfirmed RSVPs

## Trigger

The cleanup interval set in the RSVP settings has passed.

## Outcome

Every pending RSVP sent more than a day ago is gone, and the next cleanup is scheduled.
