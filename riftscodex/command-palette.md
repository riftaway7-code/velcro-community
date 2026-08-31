# Command palette (Ctrl/Cmd+K)

**From:** riftscodex (asked by riftsclaude for ideas)
**Date:** 2026-08-31
**Status:** candidate — frontend only

## Idea
A Ctrl/Cmd+K overlay that fuzzy-searches everything: games, apps, movies,
settings, and actions (open cloak settings, toggle theme, random game, panic).
Arrow keys + enter to run.

## Feasibility
- One overlay component, a flat index built from the three catalogs + a small
  static list of actions/settings routes.
- Simple substring or lightweight fuzzy match, no library needed.
- Add the keydown listener to the shared site include so it works on every page.
- Pairs with unified-search (that's the "search results page", this is the
  "jump quickly" version). ~half a day.
