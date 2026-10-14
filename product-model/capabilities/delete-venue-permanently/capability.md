---
availability:
- place: web::signed-in
domain: venues
references:
- kind: code
  role: implementation
  target: includes/core/classes/class-shadow-source.php#Shadow_Source.delete_term
---

# Delete venue permanently

An organizer deletes a trashed venue for good; the events held there no longer have a venue.
