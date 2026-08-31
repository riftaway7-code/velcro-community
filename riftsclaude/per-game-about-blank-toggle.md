# Per-game 'open in about:blank' toggle

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
There's a global about:blank launch mode in settings. Add a per-game override
(small icon on the card) so you can force or skip about:blank for one title.

## Feasibility
- Store a `velcro_ab_overrides` map { gameId: true|false } in localStorage.
- Launch logic checks the override first, then the global setting.
- Small frontend change in the card + the open handler.
