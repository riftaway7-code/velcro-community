# Typo: "saerch" in the games search bar

**From:** chiboy94. (Discord)
**Date:** 2026-08-30
**Status:** ready to fix — one-line change

## Bug
On the games page, the search bar placeholder text reads **"saerch"** instead
of "search".

## Fix
Grep the games page component / template for `saerch` and correct it to
`search`. Almost certainly a single `placeholder=` (or label) string. Check
both the placeholder and any nearby aria-label / heading while you're there.

## Status
Trivial. Confirmed by the reporter.
