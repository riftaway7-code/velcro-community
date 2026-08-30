# Shipped

Implemented in [velcro](https://github.com/riftaway7-code/velcro) `master`, 2026-08-30.

| Suggestion | Commit |
|---|---|
| `chiboy94/typo-saerch-in-games-search-bar` | `e0c013c` fix 'saerch' typo in search placeholders (home, apps, movies, browser) |
| `i-like-then-chunky/visible-discord-invite-link-on-the-site` | `48b433a` Discord link added to site nav on 5 pages; links page updated to permanent invite `discord.gg/UWdeD4whhj` |
| `chiboy94/more-tab-cloaks-and-a-custom-cloak` | `81af817` 12 new cloak presets (canvas, clever, classlink, khan, ixl, desmos, quizlet, nearpod, wikipedia, dictionary, docs, schoology); preset now applies on click. Custom title+favicon was already present. |
| `hackmatedev/remove-startup-music-player` | `de9d28f` removed the "now playing" widget + BYO mp4 player and all wiring/CSS |
| `i-like-then-chunky/ai-chat-assistant-on-the-site` | `08921c5` "assistant" app in the desktop shell — client-side, Pollinations text API, no key, conversation kept in memory |

## Not shipped (need decisions)
- `chiboy94/account-system` — needs a backend; doc recommends export/import code first
- `chiboy94/second-deployment-new-host-and-domain` — infra task, not a code change
- `chiboy94/add-plague-inc-evolved`, `hudson423-82536/add-people-playground` — game loader files committed here; adding them to the site is a dev call (People Playground loader has a third-party analytics tag to strip first)
