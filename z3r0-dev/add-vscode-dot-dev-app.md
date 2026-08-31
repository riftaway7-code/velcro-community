# Add vscode.dev to the apps list

**From:** z3r0_dev (Discord)
**Date:** 2026-08-31
**Status:** wanted — small add, needs a proxy test

## Ask
Add vscode.dev (browser VS Code) as an entry in the apps section for coding on
a locked-down machine.

## Feasibility
- Mechanically it's one row in `apps.json`:
  `{ id: "vscode", title: "VS Code", url: "https://vscode.dev",
     thumbnail: "<vscode favicon>", category: "Productivity" }`
- The catch: vscode.dev is a heavy SPA that registers its own service worker and
  uses web workers + WASM. Loading that *through* scramjet/UV can conflict with
  velcro's proxy service worker. Test both:
  - direct iframe (may work if the network doesn't block vscode.dev)
  - through the proxy (more likely to break on the SW; try UV vs scramjet)
- If neither is stable, mark it as "open in new tab" rather than embedded.

## Notes
- Files opened in vscode.dev are local-only (File System Access API) or a GitHub
  repo — no server needed on velcro's side.
