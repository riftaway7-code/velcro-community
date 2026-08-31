# Add itch.io HTML5 games to the catalog

**From:** z3r0_dev (Discord)
**Date:** 2026-08-31
**Status:** wanted — a curation task, no backend

## Ask
Pull free browser games from itch.io into the Velcro games list.

## Why it fits
- itch.io hosts thousands of free HTML5 games, most playable straight in an
  iframe from `html.itch.zone` / the game's own itch page.
- Reputable platform, games are posted by their devs, no proxy needed for the
  ones that allow embedding.

## Feasibility
- Just more `games.json` entries: `{ id, title, url, thumbnail, category }`
  where `url` is the itch.io play/embed URL.
- Curation is the work — pick games, grab the embed URL + a thumbnail, test
  each one loads in an iframe (some devs disable embedding; skip those).
- The existing `game.html` already handles arbitrary URLs; itch pages that
  need it can still go through the proxy, ones that don't can be marked local.
- No backend, no new code beyond catalog entries. Could batch 20-50 at a time.

## Notes
- Prefer games with a permissive embed setting and a decent thumbnail.
- Tag them (arcade / puzzle / horror / etc.) so they slot into the category
  pills.
- Good candidate for a small script that reads a list of itch URLs and spits
  out games.json rows.
