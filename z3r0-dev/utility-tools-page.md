# Utility tools page

**From:** z3r0_dev (Discord, list drafted with Gemini)
**Date:** 2026-08-31
**Status:** wanted — all client-side, one page

## Ask
A `/tools.html` with a set of small utilities. From the submitted list, the ones
worth building:

- **Proxy / IP checker** — shows your public IP, rough location, and ISP (one
  call to a free API like ipapi.co). Useful to confirm the proxy is actually
  routing.
- **Word & character counter** — live counts, reading-time estimate, for essays.
- **Case converter** — UPPER / lower / Title / aLtErNaTiNg.
- **Lorem ipsum generator** — n paragraphs of placeholder text.
- **Unicode font styler** — turns text into �física / 🅱️ubble / etc. styles
  (harmless novelty).
- **Audio visualizer** — drop an MP3, canvas visualizer reacts to it via the Web
  Audio API. Fully local.
- **Ping / latency test** — times a fetch to a few endpoints, shows ms.

## Feasibility
- Every one of these is client-side JS, no backend. IP checker and ping hit a
  public endpoint; the rest are pure local.
- One page, tabbed or stacked cards, reuse site styling. Add a "tools" nav entry.
- ~a day for the batch.

## Explicitly NOT included (from the same list)
- History flooder — spamming the user's own browser history is exactly what
  school monitoring software flags on. Actively harmful.
- Inspect-element blocker — user-hostile, trivially bypassed, breaks nothing for
  anyone technical.
- Auto-destruct tab on idle — fires while reading/watching. Annoying.
- "AI humanizer / rewriter" to beat AI-detection on essays — academic-dishonesty
  tool, not building it.
- CORS bypass — velcro already has `/api/fetch`.
