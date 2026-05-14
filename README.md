# Engram plugin for Claude Code

Persistent, explainable memory for Claude Code via the [Engram](https://lumetra.io) MCP server.

## Install

```
/plugin marketplace add lumetra-io/engram-plugin
/plugin install engram@lumetra
```

You'll be prompted for `ENGRAM_API_KEY`. Get one at [lumetra.io](https://lumetra.io) — free tier, no card.

## What you get

- The Engram MCP server pre-wired with auth (no `~/.claude.json` editing).
- `/engram-remember <fact>` — store a fact in memory.
- `/engram-recall <query>` — search memory in natural language.

The MCP server also exposes `store_memory`, `query_memory`, `list_buckets`, `delete_memory`, and `clear_memories` to Claude directly — the slash commands are just shortcuts.

## BYOK reminder

Engram is bring-your-own-key. Configure an OpenAI / Anthropic / Groq / Together / Fireworks key on the [Lumetra portal](https://lumetra.io/models) before your first `store_memory` call, or every request returns HTTP 412.

## License

MIT — see [`plugins/engram/.claude-plugin/plugin.json`](plugins/engram/.claude-plugin/plugin.json).
