# Add People Playground

**From:** hudson423._82536 (Discord)
**Date:** 2026-08-30
**Status:** ready to add — file is in this folder, one thing to strip first

## Ask
Add People Playground to the Velcro library. File: `People_Playground.html`
(committed alongside this doc).

## What the file is
A ~23 KB Unity WebGL loader. Standalone (no local Build folder needed), but
streams all assets at runtime from a third-party mirror:
- `<base>` = `cdn.jsdelivr.net/gh/bubbls/ugss@main/people-playground/`
- also loads `cdn.jsdelivr.net/gh/bubbls/UGS-Assets@main/merge.js`
- Unity, "Studio Minus" / "People Playground" v1

## For whoever picks this up
- **Strip the analytics.** The loader embeds a Google Analytics tag
  (`googletagmanager.com/gtag/js?id=G-L7856P3VNT`) that is not ours — it's
  phoning user data to whoever made the mirror. Remove that script + gtag init
  before adding the file.
- Works as-is otherwise, but dies if `bubbls/ugss` or `bubbls/UGS-Assets` gets
  deleted or jsDelivr is blocked. Mirror the assets to Velcro's own host and
  repoint `<base>` if that matters.
- People Playground assets are large; check first-load size.
- Test on a school network in case jsDelivr is filtered.

## Status
Wanted, file provided. Strip the analytics, add it, load-test.
