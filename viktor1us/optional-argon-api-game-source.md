# Optional: pull games from the Argon API

**From:** viktor1us__ (Discord) — author of the API
**Date:** 2026-09-01
**Status:** speculative — API not shipped yet, revisit when it's live

## Ask
Add Argon (github.com/ViktoriusOnTop/argon) as a game source for Velcro. It's a
Rust games catalog + search API the submitter is building. Public hosting ETA
~5 days from 2026-09-01.

## What it provides (per submitter)
- Search: 10 req/s per IP, returns JSON `{ id: u64, name, main_img,
  game_recommend_img, game_icon }`.
- Auth: currently issues an `sn` + `token` that must be passed on each request
  (may move to a different DB / auth model — not finalised).
- Not just an index — returns **WebRTC URLs** for the games (so the games are
  streamed/hosted, not iframed static HTML).
- Planned later: cross-proxy chat.

## Feasibility / concerns
- **Not shippable yet.** API isn't public, response shape and auth are still
  changing by the submitter's own account. Nothing to integrate against.
- **WebRTC delivery is a different model** from how Velcro runs games today
  (static HTML in an iframe, or proxied http). A WebRTC game stream needs a
  client that negotiates the peer connection — that's real new frontend work,
  not a `games.json` row.
- **Third-party dependency.** If Argon's host goes down or the maintainer stops,
  every game sourced from it breaks. Same risk noted on the jsDelivr-mirror
  game loaders.
- **Per-request token auth** means Velcro would be shipping a client that holds
  an Argon credential, or proxying every search through velcro's own backend.
- Trust: evaluate the API's content and terms before pointing users at it.

## Recommendation
Hold. Re-open this once Argon is actually live with a stable, documented
response format and auth model. At that point decide: (a) index-only — ingest
its search results as normal catalog entries pointing at plain URLs, cheap; or
(b) full WebRTC client — only worth it if there's real demand and the API
proves reliable.
