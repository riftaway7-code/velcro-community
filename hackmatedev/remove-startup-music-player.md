# Remove the startup music player

**From:** hackmatedev (Discord)
**Date:** 2026-08-30
**Status:** proposed — ready to build

## Original ask
"Remove the little music player that pops up at the very start."

## Refined proposal
Delete the music player entirely — both the auto-popup on first load and the
underlying "load your own audio file" component. Not a settings toggle, not a
menu button. Full removal.

## Rationale
- The annoyance is the popup appearing on every first load, not the audio.
- It's a bring-your-own-file player (expects an mp3/mp4 in the user's drive).
  On locked-down school accounts nobody has media files lying around, so real
  usage is effectively zero.
- There's no hosted playlist to preserve, so nothing is worth keeping behind a
  setting.

## Feasibility
- Frontend-only. Remove the component, its mount/trigger on load, and any
  related state or localStorage keys.
- Low risk: no other feature depends on it. Quick check for a shared audio
  context or global volume setting that other UI might reuse (unlikely).
- Drop its assets too (icons, default track reference) to keep the bundle clean.

## Open questions
- Any keyboard shortcut or URL param that opens it? Remove those as well.
