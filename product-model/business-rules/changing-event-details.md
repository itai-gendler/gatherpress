---
appliesTo:
- type: entity
  id: event
  effect: changes
  facts:
  - Title
  - Description
  - Featured image
  - Start
  - End
  - Timezone
  - All day
  - Append time zone
  - Venue
  - Topics
  - Online event
  - Online event link
  - RSVP enabled
  - Open RSVP
  - Anonymous RSVP
  - Capacity
  - Guest limit
  - RSVP form questions
  - Publish date
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: writes
    entity: author
references:
- kind: doc
  role: intent
  target: docs/user/user-roles-and-permissions.md
- kind: code
  role: implementation
  target: includes/core/classes/class-utility.php#Utility.can_edit_post_meta
---

# An event's details are changed by its author, an editor or an administrator

Editors and administrators change any event; an author changes the events they wrote. The Product's own background work on an event counts as the person whose action caused it.
