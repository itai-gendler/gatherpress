---
availability:
- place: web::public
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-form.php#Form.process_rsvp
- kind: code
  role: implementation
  target: includes/core/classes/event/class-rest-api.php#Rest_Api.handle_rsvp_form_submission
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-rsvp-form.php#Rsvp_Form.validate_custom_fields
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-token.php#Token.send_rsvp_confirmation_email
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
- kind: doc
  role: intent
  target: docs/user/blocks/form-field.md
---

# RSVP without an account

A visitor RSVPs to an event with only a name and email address through its RSVP form, answering the organizer's questions and choosing guests, anonymous listing and event emails. The RSVP waits unconfirmed until they follow the link emailed to them or an editor approves it. Available while Open RSVP is on for the site and the event.
