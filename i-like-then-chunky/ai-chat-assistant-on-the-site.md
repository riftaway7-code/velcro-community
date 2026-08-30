# AI chat assistant on the site

**From:** i_like_then_chunky (Discord)
**Date:** 2026-08-30
**Status:** wanted — doable with no backend and no API key

## Ask
A ChatGPT-style assistant built into Velcro. Use case: homework help on a
locked-down machine where the real ChatGPT is blocked.

## Refined proposal
A chat panel (dedicated page or slide-out) where you type a question and get a
streamed answer. Keep recent conversation in localStorage. No login needed.

## Feasibility — no key, no backend, client-side only
Two free options, both a `fetch` from the static frontend:
- **Pollinations text API** — `https://text.pollinations.ai/openai`
  (OpenAI-style POST) or `GET https://text.pollinations.ai/<prompt>`. Free, no
  key. Same provider as the image feature already in use here.
- **Puter.js** — one `<script>` tag, then `puter.ai.chat(prompt)`. Free, no
  key, "user pays" model. Purpose-built for exactly this.

Pick one, wire a chat UI, done. No accounts, no server.

## Watch out for
- The AI endpoint's own domain (pollinations.ai / puter.com) can get filtered
  on a school network — then the feature is dead there. Nothing to do about it
  except maybe fall back between the two providers.
- Free services are slow/flaky under load. Show a proper loading + error state.
- Streaming is nicer than a 10-second blank wait; both providers support it.

## Status
Wanted. Straightforward frontend feature once a provider is picked.
