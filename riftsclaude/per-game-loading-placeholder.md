# Per-game loading placeholder

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
While a proxied game boots, show a skeleton / spinner with the game's name and art
instead of a blank white iframe.

## Feasibility
- Overlay a div on the game iframe container; remove it on iframe `load` (or after
  a max timeout with a 'still loading / retry' state).
- Pull name + thumb from games.json.
- Pure frontend, ~1 hour. Big perceived-speed win.
