# Client configuration snippets

Every file connects the same hosted server, `https://api.truthifi.com/mcp`. Nothing to install or run; your client opens a browser for you to sign in to Truthifi.

| Client | File | Where it goes | Sign-in tested |
|---|---|---|---|
| Claude (web or desktop; then on mobile) | none | Customize → Connectors → + → Add custom connector (Free: one custom connector). On Team/Enterprise an Owner adds it first under Organization settings → Connectors | Yes |
| ChatGPT (web) | none | Settings → Apps → Advanced settings → Developer mode (some accounts: Settings → Security and login), then create an app, paste the URL, choose OAuth. Plans are set by OpenAI | Yes |
| Claude Code | `claude-code.mcp.json` | project `.mcp.json`, or `claude mcp add --transport http truthifi https://api.truthifi.com/mcp` | Yes |
| Cursor | `cursor.mcp.json` | `~/.cursor/mcp.json` or project `.cursor/mcp.json` | Yes |
| VS Code / GitHub Copilot | `vscode.mcp.json` | `.vscode/mcp.json` in your project, or the README install button | Yes |
| GitHub Copilot CLI | `copilot-cli.mcp-config.json` | `~/.copilot/mcp-config.json`, or `copilot mcp add --transport http truthifi https://api.truthifi.com/mcp` | To confirm |
| Windsurf / Devin Desktop (default agent) | `devin-local.mcp_config.json` | `devin mcp add -s user truthifi https://api.truthifi.com/mcp` then `devin mcp login truthifi` (`~/.config/devin/mcp_config.json`) | To confirm |
| Windsurf / Devin Desktop (legacy Cascade agent) | `windsurf.mcp_config.json` | `~/.config/devin/mcp_config.json` (Windows `%APPDATA%\devin\mcp_config.json`); older Windsurf builds: `~/.codeium/windsurf/mcp_config.json` | To confirm |
| Google Antigravity | `antigravity.mcp_config.json` | `~/.gemini/config/mcp_config.json` or workspace `.agents/mcp_config.json` | To confirm |
| Gemini CLI | `gemini-cli.settings.json` | `~/.gemini/settings.json`, or `gemini extensions install https://github.com/truthifi/truthifi-mcp` | To confirm |
| OpenAI Codex | `codex.config.toml` | `~/.codex/config.toml`, or `codex mcp add truthifi --url https://api.truthifi.com/mcp` | To confirm |
| Kiro | `kiro.mcp.json` | `~/.kiro/settings/mcp.json` or `.kiro/settings/mcp.json`; or Powers → Import power from GitHub → this repo | To confirm |
| Zed | `zed.settings.json` | Zed settings (`context_servers`), or Settings → AI → MCP Servers → Add Remote Server | To confirm |
| JetBrains AI Assistant | `jetbrains-ai-assistant.mcp.json` | Settings → Tools → AI Assistant → Model Context Protocol (MCP) | **OAuth untested** |
| JetBrains Junie (IDE and CLI) | `junie.mcp.json` | `~/.junie/mcp/mcp.json` or `.junie/mcp/mcp.json`; then Authorize | To confirm |
| OpenCode | `opencode.json` | `opencode.json` (`mcp` section); if needed `opencode mcp auth truthifi` | To confirm |
| Charm Crush | `crush.json` | `crush.json` (needs `"oauth": true`) | To confirm |
| Warp | `warp.mcp.json` | Settings → MCP Servers → + | To confirm |
| Amazon Q Developer (IDE) | `amazon-q.mcp.json` | Q chat → MCP servers → + → Transport http (file: `~/.aws/amazonq/default.json`) | To confirm |
| Perplexity | none | [perplexity.md](perplexity.md) | To confirm |
| Microsoft Copilot Studio | none | [copilot-studio.md](copilot-studio.md) | To confirm |
| Mistral Le Chat | none | [le-chat.md](le-chat.md) | To confirm |
| Cline | `cline.mcp_settings.json` | Cline → MCP Servers → Configure | **OAuth untested** |
| Goose | `goose.config.yaml` | `~/.config/goose/config.yaml` | To confirm |
| Continue | `continue.config.yaml` | `.continue/mcpServers/truthifi.yaml` | **OAuth untested** |
| LM Studio | `lm-studio.mcp.json` | Program → Install → Edit mcp.json, or `lmstudio://add_mcp?name=truthifi&config=eyJ1cmwiOiJodHRwczovL2FwaS50cnV0aGlmaS5jb20vbWNwIn0%3D` | To confirm |
| Claude Desktop (old builds only) | `legacy/claude-desktop-via-mcp-remote.json` | Uses the third-party `mcp-remote` package, pinned to `mcp-remote@0.14.3` (re-test before each pin change). Prefer the built-in connector | Legacy |

Field names differ by client (`url`, `httpUrl`, `serverUrl`, `uri`) but the server is the same. Step-by-step guides: <https://truthifi.com/connect>.
