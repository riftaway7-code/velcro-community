# Argon as the backend for the account system

**From:** viktor1us__ (Discord) — author of Argon
**Date:** 2026-09-01
**Status:** speculative — depends on unshipped Argon features; ties to chiboy94/account-system

## Ask
chiboy94's `account-system.md` was blocked because Velcro has no backend / no
persistence. viktor is adding an account system to the Argon API and suggests
Velcro use that instead of standing up its own.

## What this would give
- Auth + per-user storage handled by Argon, so Velcro stays a static frontend.
- Would cover the same wants from account-system.md: cross-device sync of
  settings, cloak config, favorites, per-game progress.

## Feasibility / concerns
- **Doesn't exist yet.** Argon's account system is "soon", the core API isn't
  even public (see `optional-argon-api-game-source.md`). Nothing to build
  against.
- **Hard dependency on a third party.** If Argon goes down or the maintainer
  moves on, every Velcro account and everyone's synced data is gone. That's a
  bigger blast radius than the game-source dependency.
- **Trust + data.** Velcro would be handing user accounts (and whatever's
  synced) to an external service. Need its terms, its data handling, where it's
  hosted, and a migration/export path before committing.
- **School networks.** If Argon's domain is filtered, login breaks — same risk
  flagged in account-system.md for Supabase. Design localStorage-first with
  Argon sync as an optional layer, never a hard requirement.
- The cheap interim from account-system.md (export/import settings code, no
  backend) still stands regardless of what backend eventually lands.

## Recommendation
Keep `chiboy94/account-system.md` as the tracking issue. Note Argon as one
candidate backend alongside Supabase / a self-hosted DB. Evaluate for real only
once Argon's account API is live, documented, and stable — then compare on
reliability, data ownership, and export.
