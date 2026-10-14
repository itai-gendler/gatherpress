---
id: gatherpress
summary: 'A community event plugin for WordPress: publish events with dates, venues and online links, collect RSVPs with guests and a waiting list, and keep attendees informed by email and calendar feeds.'
category: events
tags:
- events
- rsvp
- wordpress-plugin
- community
- meetups
authors:
- name: GatherPress contributors
  url: https://github.com/GatherPress/gatherpress
license: GPL-2.0-or-later
limitations:
- 'There is no payment or ticketing: an RSVP records that a person intends to come, nothing is bought.'
- Who may create, edit and moderate follows the site's WordPress roles and capabilities; GatherPress adds no permission system of its own.
- 'Recurring events are not built in: every occurrence is its own event.'
- Email is sent through the site's own WordPress mail setup, so delivery depends on the host or a mail plugin.
- An online event carries only a link to a meeting room that lives on another service.
references:
- kind: doc
  role: intent
  target: README.md
  title: GatherPress README
- kind: doc
  role: intent
  target: readme.txt
  title: WordPress.org plugin description
- kind: doc
  role: intent
  target: docs/user/core-concepts.md
- kind: doc
  role: intent
  target: docs/user/rsvp-system.md
- kind: doc
  role: context
  target: docs/developer/philosophy/README.md
---

# GatherPress

GatherPress turns a WordPress site into a home for a community's events. Organizers publish events with a date, time and timezone, a reusable venue with an address and map, an online meeting link, or both, and arrange the page in the block editor. Members RSVP with their account and visitors without one RSVP by email and confirm through a link; each response can bring guests, be listed anonymously and answer the organizer's questions. Events can cap attendance, and when they are full new responses join a waiting list that is promoted automatically as places open. Organizers moderate and check in RSVPs, email attendees or every member about an event, and the site publishes per-event calendar downloads and live calendar feeds for the whole site, a venue or a topic.

## Intent

"Running a meetup, a user group, a conference, or a class? GatherPress gives you what you need to publish events, collect RSVPs, and keep everyone in the loop, all from your own WordPress site. Your events live on your site. You own the data, you control how it looks, and you keep the relationship with the people who show up." It is built by and for the WordPress community and follows the WordPress way wherever it can: events and venues are posts, RSVPs are comments, and permissions are WordPress capabilities.
