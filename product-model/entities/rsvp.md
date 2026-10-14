---
domain: rsvps
references:
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-rsvp.php
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/class-storage.php
- kind: code
  role: implementation
  target: includes/core/classes/rsvp/flag/class-check-in.php
- kind: doc
  role: context
  target: docs/developer/rsvp/README.md
---

# RSVP

One person's response to one event: whether they are coming, with how many guests, how they want to be listed and their answers to the event's questions.

## Information kept

- **Name** — the name the person responded with
- **Email** — the email address the person responded with
- **Type** — Member for a signed-in account, Email for a response sent without one
- **Guests** — how many people they bring besides themselves
- **Anonymous** — whether they asked to be listed as anonymous
- **Answers** — their answers to the event's RSVP form questions
- **Event updates** — whether a person without an account wants event emails
- **Approval** — Approved, Pending or Spam; only approved RSVPs count and are listed
- **Checked in** — whether they were checked in at the event
- **Submitted at** — when the response was first made

## States

### Attending

Coming, with their guests counted against the capacity.

### Waiting list

Wants to come but the event is full; waits in the order they joined.

### Not attending

Said they are not coming.
