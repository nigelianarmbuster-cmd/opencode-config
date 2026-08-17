# OpenCode Config

The shared OpenCode agent setup: supervisor + ~43 tiered agents (DeepSeek V4 Pro juniors/mules, Claude Sonnet 5 mid, Claude Opus 4.8 senior, Gemini flash/pro, Ollama local), the `observer-bridge.js` screenshot plugin, and a dormant MCP server catalog.

**Who is this for:** anyone mirroring the setup — clone into `~/.config/opencode` (`%USERPROFILE%\.config\opencode` on Windows) and run `npm install`.

**Beginner setup:** see the explainer and guides in the sibling repo `agent-orchestration` (https://github.com/nigelianarmbuster-cmd/agent-orchestration).

## Dormant by design

All MCP servers ship with `"enabled": false` (playwright, chrome-devtools, elevenlabs, yt-dlp, vercel, gemini-api-docs, context7, github, macos-use, railway). Nothing is broken — flip `"enabled": true` in `opencode.json` for the tools you use.

## Maintainer's local override (do not "fix" this)

The maintainer's machine re-enables the Railway MCP via a **personal config override**, not by editing `opencode.json`:

- File: `C:\Users\Nigel\.config\opencode-personal.json` (outside this repo, never committed)
- Env var (persistent, user-level): `OPENCODE_CONFIG=C:\Users\Nigel\.config\opencode-personal.json`
- Effect: OpenCode merges configs (later sources override conflicting keys), so Railway is enabled locally while this repo keeps the beginner default.

When changing `opencode.json` in this repo, always verify the local working copy stays at the beginner default (`railway.enabled: false`) before committing.
