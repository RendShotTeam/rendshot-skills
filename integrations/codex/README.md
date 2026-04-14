# Rendshot Skills for OpenAI Codex

## Setup

1. Clone this repo into your project or reference the skills directory
2. Set `RENDSHOT_API_KEY` environment variable
3. Reference skill files in your Codex configuration

## MCP Server

Add to your MCP configuration:

```json
{
  "mcpServers": {
    "rendshot": {
      "command": "npx",
      "args": ["-y", "@rendshot/mcp"],
      "env": {
        "RENDSHOT_API_KEY": "your_api_key"
      }
    }
  }
}
```

## Skills

The `skills/` directory contains platform-agnostic markdown guides:

- `skills/rendshot/` — Core tool usage (MCP, API, CLI, SDK)
- `skills/xiaohongshu/` — Xiaohongshu content strategy + design
- `skills/instagram/` — Instagram content strategy + design

Point your agent to the relevant SKILL.md files as system context.
