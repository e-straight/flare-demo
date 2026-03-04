# Agents Instructions

## Live Demo Workflow

When the user asks to create a live demo, interactive page, or any visual web artifact:

### Keep It Simple

Demos should be **simple, focused, and quick to build**. Prioritize clarity over complexity — a clean, working single-page demo is better than an overengineered multi-component project. Aim to have something running in Chrome within minutes, not hours.

### 1. Build with the Frontend Design Skill

Use the `frontend-design` skill to generate polished UI. Keep the scope tight — one HTML file with inline styles/scripts is perfectly fine for a demo.

### 2. Launch a Local Server

Start a local development server using bash with `mode: "async", detach: true` so it persists:

- For static HTML: `bunx serve .` or `python3 -m http.server`
- For framework projects: use the appropriate dev server (`bun run dev`, `npm run dev`, etc.)

Note the localhost URL and port for the next step.

### 3. Verify in Google Chrome

After launching, use the Chrome DevTools MCP tools to inspect and validate the page:

1. **Navigate** to the localhost URL using `navigate_page`
2. **Take a screenshot** with `take_screenshot` to visually verify the result
3. **Check console messages** with `list_console_messages` — look for errors or warnings
4. **Check network requests** with `list_network_requests` — look for failed fetches or 404s

### 4. Iterate Until Correct

If the screenshot reveals visual issues or the console shows errors:

- Fix the underlying code
- Reload the page (`navigate_page` with `type: "reload"`)
- Re-verify with screenshot and console checks

Do not consider the task complete until the page renders correctly with no console errors.
