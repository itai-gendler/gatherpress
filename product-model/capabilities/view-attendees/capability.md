---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/core/classes/blocks/class-rsvp-response.php#Rsvp_Response
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/response/class-serializer.php#Serializer.to_array
- kind: doc
  role: intent
  target: docs/user/blocks/rsvp-response-and-inner-blocks.md
---

# View attendees

Anyone sees who is coming to an event in its attendee list, switching between attending, waiting list and not attending, with each person's role and guests. Only approved RSVPs are listed.
