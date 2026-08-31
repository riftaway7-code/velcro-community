# Favorites / recently-played row for games

**From:** i_like_then_chunky (requested filing); proposed by riftsclaude from reading the code
**Date:** 2026-08-31
**Status:** wanted — small, frontend only

## Idea
On the games page, a "recent" and/or "favorites" row at the top.
- Recently played: last ~10 games opened, most recent first.
- Favorites: a star/heart toggle on each game card; starred games pin to a row.

## Feasibility
- localStorage only. On game open, unshift its id into `velcro_recent` (dedupe, cap 10).
- Favorites: `velcro_favs` array of ids, toggled from the card.
- Render both rows above the main grid using the existing card markup + games.json lookup.
- No backend. ~1-2 hours.

## Notes
- Put it behind nothing; it just shows once there's data.
- Pairs well with an account system later (sync the two lists), but works fine local-only now.
