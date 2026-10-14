---
availability:
- place: web::administration
- place: wp-cli
domain: settings
references:
- kind: code
  role: implementation
  target: includes/core/classes/settings/class-tools.php#Tools
- kind: code
  role: implementation
  target: includes/core/classes/commands/class-settings-cli.php#Settings_Cli.import
- kind: doc
  role: intent
  target: docs/developer/wp-cli/README.md
---

# Import settings

An administrator or operator reads GatherPress settings back in from an exported file, after a preview, either merging with the current settings or replacing them.
