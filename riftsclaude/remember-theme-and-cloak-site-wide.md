# Remember theme + cloak across the whole site

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
Theme toggle and cloak already persist in places, but not consistently across
every page (desktop shell vs home vs apps vs movies). Make one shared init so the
saved theme + cloak apply everywhere on first paint, no flash.

## Feasibility
- Consolidate theme.js + cloak.js reads into a single early inline script included
  on every page `<head>` before CSS, to avoid FOUC.
- Mostly a refactor + making sure every html includes it. ~half a day.
- Sets up nicely for account sync later.
