---
availability:
- place: web::signed-in
domain: venues
references:
- kind: code
  role: implementation
  target: includes/core/classes/venue/class-setup.php#Setup
- kind: code
  role: implementation
  target: src/components/VenueForm.js
- kind: doc
  role: intent
  target: docs/user/venues.md
---

# Create venue

An organizer adds a venue, either from Events > Venues > Add New or straight from the Venue block of an event, where the new venue is published and chosen for the event at once.
