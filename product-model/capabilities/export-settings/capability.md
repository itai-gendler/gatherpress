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
  target: includes/core/classes/commands/class-settings-cli.php#Settings_Cli.export
- kind: doc
  role: intent
  target: docs/developer/wp-cli/README.md
---

# Export settings

An administrator or operator writes the GatherPress settings out as a file, to copy them to another site or keep a backup.
