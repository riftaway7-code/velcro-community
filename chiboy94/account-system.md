# Account system

**From:** chiboy94. (Discord)
**Date:** 2026-08-30
**Status:** wanted — but largest scope so far, needs a backend decision first

## Ask
Add user accounts. Purpose: "all" — cross-device sync of settings, cloak
config, favorites / games list, and per-game progress.

## Refined proposal
- Auth + a per-user data store.
- Store per user: settings blob, cloak config, favorites list, per-game save
  data / last played.
- Load on login, write on change.

## Feasibility

Velcro is a static frontend today, so this needs a backend.

**Recommended: Supabase** (already used in r-ubg). Auth + one `user_data` table
with a JSON column. Free tier is plenty for this. Least new infra.

**Lighter alternative if accounts aren't worth it yet:** keep everything in
localStorage (as now) and add an "export / import settings code" — a
base64 string of the whole config the user can paste on another device. No
backend, no auth to secure, solves the cross-device pain for ~an hour of work.

## Watch out for
- It's a UBG site used on school networks. If Supabase's domain is blocked
  there, login breaks. Design localStorage-first with account sync as an
  optional layer, not a hard dependency.
- Keep PII minimal. Options, roughly in order of least hassle:
  - Anonymous account: random id in localStorage, optional email later to
    claim/recover it.
  - Email + password: you own password resets.
  - Google OAuth: easiest to build, but Google may be the exact thing users
    are evading on that network.
- Don't gate any existing feature behind login. Accounts are additive.

## Recommendation
Ship the export/import code first (cheap, immediate). Do full accounts only if
there's sustained demand, and if so, Supabase + localStorage-first.
