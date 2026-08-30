# More tab cloaks + a custom cloak

**From:** chiboy94. (Discord)
**Date:** 2026-08-30
**Status:** wanted — straightforward frontend work

## Ask
More options for the tab cloak feature. Both:
1. More built-in cloak presets.
2. A custom cloak where the user sets their own tab title and favicon.

## Refined proposal

### Preset library
Expand the preset list with the usual school-tool disguises, each preset being
a `{ name, title, favicon }`:
- Google Classroom, Google Drive, Google Docs
- Canvas, Schoology, Clever, ClassLink
- Khan Academy, Desmos, Quizlet, Dictionary.com, Wikipedia
Keep the current ones. Bundle the favicons locally so none depend on an
external host.

### Custom cloak
- Two inputs in settings: tab title, and favicon (either paste a URL or pick
  from the bundled preset icons).
- Persist the choice to localStorage and re-apply on every load.
- "Reset to default" button.

## Feasibility
- Cloaking is just `document.title = ...` plus swapping the
  `<link rel="icon">` href. Presets are a static array; custom is 2 fields +
  persistence. Low effort, no backend.
- Favicon-by-URL can break (dead link, CORS). Offering the bundled icon picker
  as the default path avoids that; keep URL as an advanced option.
- Confirm the cloak already applies on load so a saved custom cloak survives a
  refresh.

## Open questions
- chiboy94 said "some [more] ill think of later" — leave room to append preset
  ideas to this file.
