# Random game button

**From:** riftsclaude (proposed from reading the velcro code; filed at i_like_then_chunky's request)
**Date:** 2026-08-31
**Status:** candidate — frontend only unless noted

## Idea
A 'surprise me' button that opens a random game from the (filtered) list.

## Feasibility
- One button, `list[Math.floor(Math.random()*list.length)]`, call the existing
  open handler. 10 minutes.
- Respect active category filters if #5 lands.
