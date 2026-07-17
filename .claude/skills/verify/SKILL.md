---
name: verify
summary: Drive the Astro site in Chromium and capture route evidence.
---

1. Ensure the Astro dev server is running with `npx astro dev status`; start it with `npm run dev -- --host localhost --port 4321` if needed.
2. Use `http://localhost:4321` (not `127.0.0.1`, which may not reach Astro's running server in this environment).
3. Drive the changed pages in headless Chromium. If unavailable, install it once with `npx --yes playwright install chromium`; then locate the temporary package with `find ~/.npm/_npx -type d -path '*/node_modules/playwright' -print | tail -1` and set its parent `node_modules` directory as `NODE_PATH` for a short Playwright script.
4. Capture screenshots in `/tmp`, inspect them, and exercise navigation, keyboard-visible controls, theme persistence, and a narrow mobile viewport. Verify representative content routes plus any unaffected route named in the change.
