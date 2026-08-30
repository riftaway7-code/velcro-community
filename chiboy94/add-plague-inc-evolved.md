# Add Plague Inc: Evolved

**From:** chiboy94. (Discord)
**Date:** 2026-08-30
**Status:** ready to add — file is in this folder

## Ask
Add Plague Inc: Evolved to the Velcro library. File: `Plague_Inc_Evolved.html`
(committed alongside this doc).

## What the file actually is
A ~6 KB HTML loader for a Unity WebGL build. It is standalone in that it needs
no local `Build/` folder, but it pulls everything at runtime from
`cdn.jsdelivr.net/gh/reeyuki/PlagueIncEvolved` (a third-party GitHub repo):
- Unity `.wasm` (2 parts) + `.data` (15 parts), ~317 MB total first load
- framework.js, loader.js, StreamingAssets from the same base
- Unity version 1.18.3.2, no backend

## For whoever picks this up
- Drop the .html in and add a library entry (title, thumbnail, category).
- It works as-is, but the whole game dies if `reeyuki/PlagueIncEvolved` gets
  deleted or jsDelivr blocks it. If that matters, mirror those assets to
  Velcro's own host and repoint the `base` / `baseBuild` consts in the file.
- 317 MB first load is heavy. Fine after browser/CDN cache, but worth knowing.
- Test once on a school network in case jsDelivr is filtered there.

## Status
Wanted, file provided and committed. Add + load-test, optionally self-host the
assets.
