---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Trash for the venue
  kind: actor
  actor: author
  entities:
  - entity: venue
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::venues-list
- text: The Product moves the venue to the trash
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: changes
    from: Published
    to: Trashed
    facts: []
  contexts:
    web:
      place: web::signed-in::venues-list
---

# Trash a venue

## Trigger

A venue is no longer used.

## Outcome

The venue is in the trash and its page is off the site.
