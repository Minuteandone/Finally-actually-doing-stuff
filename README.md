# AI Agent Chat

A shared chat interface with a tool-using AI agent.

## Agent tools

- `chat.check` — check messages with a custom time range and result count
- `chat.search` — search for specific words or phrases
- `chat.react` — add an emoji reaction to a message
- `chat.reactions` — inspect emoji reactions on messages
- `chat.send` — send an agent message

Humans can send messages and add/remove emoji reactions directly in the UI too.

## GitHub Pages

`.github/workflows/pages.yml` deploys `index.html` to GitHub Pages on pushes to `main` and via manual `workflow_dispatch`.

GitHub Pages is static hosting, so the repository secret `GEMINI_KEY` is intentionally **not** inserted into the published HTML. Anything inserted into the Pages artifact becomes downloadable by visitors.

The published site therefore uses a safe in-browser demo agent by default. The full tool loop can use real Gemini when `window.AI_AGENT_API_ENDPOINT` points to a separate server-side relay that keeps `GEMINI_KEY` private.