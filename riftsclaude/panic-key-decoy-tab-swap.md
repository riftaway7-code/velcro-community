# Panic key: swap the tab to a decoy instantly

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** wanted — small, high value for the audience

## Idea
A configurable hotkey (default like the backtick or a chosen key) that instantly:
- navigates the tab to a decoy URL (Google Classroom, a blank doc, school portal), and/or
- opens the decoy in this tab and moves velcro to a background about:blank tab.

## Feasibility
- Keydown listener on a global script (add to the shared includes).
- Decoy URL + key are settings, stored in localStorage, edited on the settings page
  next to the cloak section (reuse that UI pattern).
- `window.location.replace(decoy)` for the simplest version so it doesn't leave
  velcro in history.
- Ties in with the existing "about:blank launch mode" setting.
- No backend. 1-2 hours.

## Notes
- Make the default key something unlikely to be hit by accident; let users rebind.
- Optional: second press brings velcro back (store it first).
