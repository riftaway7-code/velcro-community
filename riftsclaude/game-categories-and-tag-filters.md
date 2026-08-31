# Game categories / tag filters

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
Filter pills on the games page (arcade, io, shooter, puzzle, 2-player, retro...).
Multi-select, AND or OR, reflected in the grid live.

## Feasibility
- Needs a `tags` array per entry in games.json. If tags aren't there yet, that's
  the bulk of the work (tagging the catalog); the UI is a filter row + a filter().
- Reuse the existing `.preset-btn` pill styling.
- No backend.
