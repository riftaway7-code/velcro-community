# Keyboard navigation for the games grid

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
Arrow keys move a focus ring across game cards, Enter opens the focused game,
'/' jumps to search.

## Feasibility
- Make cards focusable (`tabindex`), track an index, handle keydown on the grid.
- Respect the current filtered/visible set.
- Accessibility win too. ~2 hours.
