---
domain: events
relations:
- entity: rsvp
  verb: receives
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: includes/core/classes/event/class-event.php
- kind: code
  role: implementation
  target: includes/core/classes/event/class-meta.php
- kind: doc
  role: intent
  target: docs/user/creating-and-managing-events.md
- kind: doc
  role: context
  target: docs/developer/data-model/README.md
---

# Event

A real-world or online gathering with a date and time, published as its own page and arranged in the block editor.

## Information kept

- **Title** — the event's name
- **Description** — the content of the event page: agenda, speakers, images and anything else added in the editor
- **Featured image** — the image shown with the event in lists and emails
- **Start** — when it starts, in its timezone
- **End** — when it ends, in its timezone
- **Timezone** — the timezone its times are kept in
- **All day** — whether it covers whole days rather than a span of hours
- **Append time zone** — Always, Never or Default: whether its timezone is printed after its date
- **Venue** — the venue it takes place at, if any
- **Topics** — the topics it is grouped under
- **Online event** — whether it can be joined online
- **Online event link** — the address attendees use to join it online
- **RSVP enabled** — whether it takes RSVPs, where the site lets each event decide
- **Open RSVP** — whether visitors without an account may RSVP to it by email
- **Anonymous RSVP** — whether people may ask to be listed as anonymous
- **Capacity** — how many people, guests included, may attend; 0 means no limit
- **Guest limit** — how many guests each attendee may bring; 0 means none
- **RSVP form questions** — the questions its RSVP form asks beyond name and email, each with its type, label, whether it is required and its options
- **Publish date** — when it goes or went live, separate from when it takes place

## States

### Draft

Being prepared; only people who may edit it see it.

### Scheduled

Set to go live at its publish date.

### Published

Live on the site, in lists and feeds.

### Trashed

In the trash, out of the site, and restorable until deleted permanently.
