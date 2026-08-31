# "Report broken game" button

**From:** i_like_then_chunky (requested filing); proposed by riftsclaude from reading the code
**Date:** 2026-08-31
**Status:** wanted — small; needs one endpoint or a webhook

## Idea
A small "report broken" link on each game (and its player page). Click sends the
game id/title so staff know what to fix or pull.

## Feasibility
- UI: one button per card / on game.html. Trivial.
- Delivery, pick one:
  - Discord webhook: POST the game title to a staff channel webhook URL. No
    backend, but the webhook URL sits in client code (rotatable, low risk).
  - Tiny endpoint: velcro already has server.js / api/index.js — add a
    `POST /api/report` that logs to a file or forwards to Discord. Cleaner, keeps
    the webhook server-side.
- Rate-limit / debounce so it can't be spammed (one report per game per session).

## Notes
- Prefer the server endpoint route since the backend already exists.
- Could show a tiny "reported, thanks" toast and disable the button after.
