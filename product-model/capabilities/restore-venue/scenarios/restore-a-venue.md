---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Restore for the trashed venue
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
- text: The Product restores the venue as a draft
  kind: product
  actor: author
  entities:
  - entity: venue
    effect: changes
    from: Trashed
    to: Draft
    facts: []
  contexts:
    web:
      place: web::signed-in::venues-list
---

# Restore a venue from the trash

## Trigger

A trashed venue is wanted again.

## Outcome

The venue is a draft again with its details.
