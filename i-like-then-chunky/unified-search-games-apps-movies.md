# One search bar across games + apps + movies

**From:** i_like_then_chunky (requested filing); proposed by riftsclaude from reading the code
**Date:** 2026-08-31
**Status:** wanted — medium, frontend only

## Idea
Right now home.html, apps.html, movies.html each have their own search that only
filters that page. Make one search that queries all three catalogs and shows
grouped results ("Games", "Apps", "Movies").

## Feasibility
- All three catalogs are static JSON (games.json, apps.json, movies.json).
- Build a small shared script that fetches all three once, does a case-insensitive
  title match, and renders grouped result cards linking into the right player.
- Could live as a new `/search.html` the nav points to, or an overlay that any
  page's search box opens.
- No backend. Half a day incl. styling.

## Notes
- Keep the per-page search too, or replace it — dev call. Overlay approach keeps both.
