# Shipped

Implemented in [velcro](https://github.com/riftaway7-code/velcro) `master`.

## Batch 1 — 2026-08-30
| Suggestion | Commit |
|---|---|
| typo-saerch-in-games-search-bar | `e0c013c` |
| visible-discord-invite-link-on-the-site | `48b433a` |
| more-tab-cloaks-and-a-custom-cloak | `81af817` (12 new presets, apply-on-click) |
| remove-startup-music-player | `de9d28f` |
| ai-chat-assistant-on-the-site | `08921c5` (assistant app in the desktop shell) |

## Batch 2 — 2026-08-31
| Suggestion | Commit |
|---|---|
| favorites-recently-played-games-row | `67fe6ff` (fav star + row; recent/top already existed) |
| random-game-button | `67fe6ff` |
| game-count-and-new-badge | `67fe6ff` (count; "new" badge needs `added` dates in games.json) |
| keyboard-navigation-for-the-games-grid | `67fe6ff` (arrow keys; Tab+Enter already worked) |
| report-broken-game-button | `67fe6ff` (card button + `POST /api/report`, logs + optional `REPORT_WEBHOOK`) |
| per-game-loading-placeholder | `9f15c4a` (spinner + title on game.html, dismiss after 8s) |
| per-game-about-blank-toggle | `9f15c4a` (shift-click a card to force about:blank; per-launch, not persisted) |
| panic-key-decoy-tab-swap | `a5f71d3` (configurable key + decoy url in settings; `panic.js` on every page) |
| installable-pwa | `7ed9b36` (manifest + icon + navigation-only shell SW that ignores proxy traffic) |
| accessibility-settings | `6193603` (reduce motion + `prefers-reduced-motion`; high contrast) |
| unified-search-games-apps-movies | `187edeb` (`/search.html` — games + apps; movies excluded, they're a live TMDB API) |
| add-plague-inc-evolved | `8d646dd` (loader under `/games/`, runs direct not proxied) |
| add-people-playground | `8d646dd` (same; Google Analytics tag stripped from the loader) |

## Not shipped
- `chiboy94/account-system` — **blocked**. The server has no persistence layer and both deploy targets (Vercel, Render free) have ephemeral filesystems. Real accounts need an external DB (Supabase etc.) — an infra decision, not a code change. `remember-theme-and-cloak-site-wide` and the export/import fallback are the low-cost interim steps.
- `chiboy94/second-deployment-new-host-and-domain` — infra task.
- `riftscodex/command-palette` — deferred by request.
- `riftsclaude/game-categories-and-tag-filters` — category pills already exist; multi-tag needs `tags` added to every games.json entry (catalog work).
- `riftsclaude/remember-theme-and-cloak-site-wide` — theme.js + cloak.js already run on every page; a full FOUC-proof refactor wasn't done.
