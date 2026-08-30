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
etc. No card required to sign up.

### Oracle Cloud (added by chiboy94)
Oracle Cloud "Always Free" gives a real ARM VM (up to 4 OCPU / 24 GB RAM) — a
full server, not just functions, so it can run a persistent proxy backend, a
database, whatever. Tradeoffs:
- Requires a payment card for identity verification at signup (not charged for
  Always Free resources).
- You manage the server (OS, updates, TLS) — more work than Pages/Vercel.
- Single region, no built-in global CDN. Put Cloudflare in front for caching.
- Oracle has reclaimed idle Always Free instances before; keep it in use.
Use this if the goal is a heavy always-on backend. Use Pages/Vercel/Netlify if
the goal is "fast static + a few functions."

### Domain
Point a fresh domain at the new deployment. ~$10/yr. A second live domain is
also useful resilience for a UBG site (school filters block domains, not the
app).

### Keeping them in sync
Deploy both from the same repo — a CI step, or connect both hosts to the branch
so a push ships to both.

## Feasibility
- Low effort for the Pages/Vercel/Netlify route if the app is already a static
  build: connect repo, set build command, add domain. An afternoon.
- Oracle route is a weekend: provision the VM, harden it, set up a web server +
  TLS + a deploy hook.
- The "more features" payoff only lands once something uses the backend (see
  account-system.md).

## Open questions
- Where is Velcro hosted right now? Decides "migrate" vs "add a parallel deploy."
- One canonical domain with the other as a mirror, or both equal?
