# Second deployment: new host + new domain

**From:** chiboy94. (Discord)
**Date:** 2026-08-30
**Status:** wanted — worth doing, mostly a setup task

## Ask
Deploy Velcro to a different host on a different domain, for two reasons:
1. A host that allows bigger features (i.e. server-side / backend code).
2. Faster response time.
Also acts as a mirror if the main domain gets filtered.

## Refined proposal
Stand up a second deployment of the same repo on an edge host that supports
serverless functions, on its own domain, kept in sync with the primary.

### Host options (all free tier, global edge, support functions)
- Cloudflare Pages + Workers
- Vercel
- Netlify

Any of these is a straight upgrade over a pure static host: fast CDN by
default, and functions unblock the account system, server-side proxy tweaks,
etc.

### Domain
Point a fresh domain at the new deployment. ~$10/yr. Having a second live
domain is also useful resilience for a UBG site (school filters block domains,
not the app).

### Keeping them in sync
Deploy both from the same repo — a CI step, or just connect both hosts to the
branch so a push ships to both.

## Feasibility
- Low effort if the app is already a static build: connect the repo, set the
  build command, add the domain. An afternoon.
- The "more features" payoff only lands once something actually uses the
  functions (see account-system.md).
- Running two hosts = two dashboards to watch, but no real ongoing cost.

## Open questions
- Where is Velcro hosted right now? That decides whether this is "migrate" or
  "add a parallel deploy."
- One canonical domain with the other as a redirect/mirror, or treat both as
  equal?
