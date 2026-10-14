---
scope: 'The GatherPress plugin: events, venues, topics, RSVPs, emails, calendar downloads and feeds, settings, profile preferences and the wp gatherpress commands.'
method: Static inspection of source and documentation at commit 926d4651; nothing was run.
covered:
- description: Event post type, dates, queries, admin list and event REST routes
  paths:
  - includes/core/classes/event/
  - includes/core/classes/class-topic.php
- description: RSVP storage, responses, providers, flags, open RSVP form, confirmation links, cleanup and the RSVPs page
  paths:
  - includes/core/classes/rsvp/
  - includes/templates/admin/rsvp/
  - includes/templates/admin/emails/
  - src/rsvp-admin/
- description: Venue post type, venue information, shadow venue terms, geocoding and maps
  paths:
  - includes/core/classes/venue/
  - includes/core/classes/class-shadow-source.php
  - includes/core/classes/class-geo-sync.php
  - includes/core/classes/class-geocoding.php
  - includes/core/classes/geocoding/
- description: Calendar downloads and iCalendar feeds
  paths:
  - includes/core/classes/calendar/
  - includes/templates/calendar/
- description: Server rendering of the event, venue, RSVP and form blocks, and the shared validation and utility helpers
  paths:
  - includes/core/classes/blocks/
  - includes/templates/blocks/
  - includes/core/templates/
  - includes/core/classes/class-utility.php
  - includes/core/classes/class-validate.php
  - includes/core/classes/class-starter-pattern-loader.php
  - includes/core/classes/class-tag-processor.php
  - includes/core/classes/settings/class-format-field.php
  - includes/templates/admin/timezone-shim.js
- description: Block editor blocks, panels and components for events, venues and RSVPs
  paths:
  - src/blocks/
  - src/panels/
  - src/components/
  - src/stores/
  - src/helpers/
  - src/index.js
  - src/editor.js
  - src/admin.scss
  - src/utility.scss
  - src/leaflet-style.js
  - src/leaflet-style.scss
- description: Settings tabs, user profile fields and WP-CLI commands
  paths:
  - includes/core/classes/class-settings.php
  - includes/core/classes/settings/class-base.php
  - includes/core/classes/settings/class-events.php
  - includes/core/classes/settings/class-venues.php
  - includes/core/classes/settings/class-rsvp.php
  - includes/core/classes/settings/class-roles.php
  - includes/core/classes/settings/class-tools.php
  - includes/core/classes/class-user.php
  - includes/core/classes/commands/
  - includes/core/classes/class-cli.php
  - includes/templates/admin/settings/
  - includes/templates/admin/user/
  - src/settings/
  - src/profile/
exclusions:
- description: Tests, CI, release tooling and build configuration
  paths:
  - test/
  - .github/
  - patches/
  - package.json
  - package-lock.json
  - composer.json
  - composer.lock
  - webpack.config.js
  - jest.config.js
  - playwright.config.js
  - phpcs.ruleset.xml
  - phpmd.xml
  - phpstan.neon.dist
  - phpstan.stubs
  - phpunit.xml.dist
  - phpunit-multisite.xml.dist
  - eslint.config.js
  - sonar-project.properties
  - wp-cron.sh
  - .coderabbit.yaml
  - .distignore
  - .editorconfig
  - .env.sample
  - .extract-wp-hooks.json
  - .gitignore
  - .markdownlintignore
  - .nvmrc
  - .stylelintignore
  - .stylelintrc.js
  - .typos.toml
  - .wp-env.json
  - .wp-env.test.json
  - jsconfig.json
- description: Plugin bootstrap, autoloading, asset loading, requirement checks and admin notices
  paths:
  - gatherpress.php
  - includes/core/classes/class-autoloader.php
  - includes/core/classes/class-assets.php
  - includes/core/classes/class-setup.php
  - includes/core/classes/admin/
  - includes/core/duplicate-check.php
  - includes/core/register-class-aliases.php
  - includes/core/requirements-check.php
  - includes/core/classes/traits/
  - includes/core/classes/class-migrate.php
  - includes/core/classes/class-renamed-keys.php
- description: WordPress.org listing, playground blueprints and documentation
  paths:
  - .wordpress-org/
  - .gatherpress-org/
  - docs/
  - README.md
  - readme.txt
  - CHANGELOG.md
  - AGENTS.md
  - CLAUDE.md
  - CODE_OF_CONDUCT.md
  - SECURITY.md
  - license.txt
unmapped:
- description: Multisite network settings and per-option inheritance
  paths:
  - includes/core/classes/settings/class-network.php
  - includes/templates/admin/settings/network-page.php
- description: Uninstall choices and the removal they drive
  paths:
  - includes/core/classes/settings/class-uninstall.php
  - includes/core/classes/uninstall/
  - uninstall.php
- description: Abilities for AI agents (upcoming events, RSVP counts)
  paths:
  - includes/core/classes/event/class-abilities.php
  - includes/core/classes/rsvp/class-abilities.php
- description: WXR import and export of event data, the WordPress feed of events and the Site Health check
  paths:
  - includes/core/classes/class-import.php
  - includes/core/classes/class-export.php
  - includes/core/classes/class-feed.php
  - includes/core/classes/class-site-health.php
- description: Credits tab
  paths:
  - includes/core/classes/settings/class-credits.php
  - includes/templates/admin/settings/credits/
  - includes/data/credits.php
- description: Query block variations, tooltip format, editor commands and third-party integrations
  paths:
  - src/variations/
  - src/formats/
  - src/commands/
  - src/integrations/
  - src/modals/
  - src/supports/
  - includes/core/classes/class-coexistence-guard.php
limitations: []
---

# Coverage
