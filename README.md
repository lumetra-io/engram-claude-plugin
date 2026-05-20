# Engram plugin for Claude Code

Persistent, explainable memory for Claude Code via the [Engram](https://lumetra.io) MCP server.

## Install

```
/plugin marketplace add lumetra-io/engram-claude-plugin
/plugin install engram@lumetra
```

You'll be prompted for `ENGRAM_API_KEY`. Get one at [lumetra.io](https://lumetra.io) — free tier, no card. The key is wired into the MCP server config via Claude Code's `user_config` mechanism (specifically `${user_config.ENGRAM_API_KEY}`) and stored in Claude Code's secret store.

## Requirements

The plugin shells out to `npx -y mcp-remote` as a stdio→SSE bridge to Engram's hosted MCP endpoint (`https://mcp.lumetra.io/mcp/sse`). You need `npx` available on `PATH` (Node.js 18+). No global install needed — `npx` fetches `mcp-remote` on first launch.

## What you get

- The Engram MCP server pre-wired with auth (no `~/.claude.json` editing).
- `/engram-remember <fact>` — store a fact in memory.
- `/engram-recall <query>` — search memory in natural language.

The MCP server also exposes `store_memory`, `query_memory`, `list_memories`, `list_buckets`, `delete_memory`, and `clear_memories` to Claude directly — the slash commands are just shortcuts.

## BYOK reminder

Engram is bring-your-own-key. Configure an OpenAI / Anthropic / Groq / Together / Fireworks key on the [Lumetra portal](https://lumetra.io/models) before your first `store_memory` call, or every request returns HTTP 412.

## License

MIT — see [LICENSE](./LICENSE).
