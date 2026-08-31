# Game count + 'new this week' badge

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
Show the total game count somewhere on the games page, and a 'new' badge on
entries added in the last N days.

## Feasibility
- Count: `list.length`, trivial.
- 'New' badge needs an `added` date field per games.json entry. If entries don't
  have dates, add them going forward and only badge the ones that do.
- Frontend + a small catalog convention. ~1 hour once dates exist.
