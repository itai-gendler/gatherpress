---
availability:
- place: web::public
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-token.php#Token.approve_comment
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-setup.php#Setup.handle_rsvp_token
---

# Confirm RSVP

A person who RSVPed without an account follows the link in their confirmation email; the RSVP is approved and counts from then on.
