# Installable PWA

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
Add a web app manifest + icons so velcro can be installed and launched like a
native app (own window, own icon, no address bar).

## Feasibility
- `manifest.webmanifest` (name, icons, start_url, display: standalone, theme).
- There's already a `sw.js`; make sure it's registered and caches the shell.
- Icon set (192/512). Link the manifest from every page head.
- The standalone window also helps hide that it's a browser tab.
- ~half a day incl. icons.
