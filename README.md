# Rendshot Skills

AI agent skills for [Rendshot](https://rendshot.com) — image generation, screenshots, and social media content creation.

These skills teach AI agents how to use Rendshot effectively, with platform-specific content strategy and design guidance.

## Skills

| Skill | Description |
|-------|-------------|
| **rendshot** | Core tool usage — MCP, API, CLI, SDK reference |
| **xiaohongshu** | Xiaohongshu (小红书) content strategy, algorithm insights, and visual design guide |
| **instagram** | Instagram content strategy, algorithm insights, and visual design guide |

## Setup

### 1. Get a Rendshot API Key

Sign up at [rendshot.com](https://rendshot.com) and create an API key in the [dashboard](https://rendshot.com/dashboard/keys).

### 2. Install for Your AI Agent

#### Claude Code

```bash
# Install as plugin (auto-configures MCP + skills)
claude plugin add RendShotTeam/rendshot-skills

# Set your API key
export RENDSHOT_API_KEY=rs_live_xxx
```

Or manually add MCP server:

```bash
claude mcp add rendshot -- npx -y @rendshot/mcp
```

#### Cursor

1. Copy `integrations/cursor/.cursorrules` to your project root
2. Add MCP server in Cursor settings:
   ```json
   {
     "mcpServers": {
       "rendshot": {
         "command": "npx",
         "args": ["-y", "@rendshot/mcp"],
         "env": { "RENDSHOT_API_KEY": "rs_live_xxx" }
       }
     }
   }
   ```

#### Codex / Other Agents

See [integrations/codex/README.md](integrations/codex/README.md) for setup instructions.

The `skills/` directory contains platform-agnostic markdown — point your agent to the relevant `SKILL.md` files as context.

## Quick Start

Once configured, your AI agent can:

```
You: "帮我做一张小红书种草封面，我卖手工皂的"

AI: [Analyzes business context → applies algorithm strategy → generates design]
    → generate_image({ prompt: "...", platform: "xiaohongshu" })
    → Returns: optimized cover image with title, layout, and colors
```

```
You: "Create an Instagram carousel about Python tips"

AI: [Applies carousel best practices → designs consistent slides]
    → generate_image({ prompt: "...", platform: "instagram_post" })
    → create_template to lock layout for remaining slides
```

## MCP Tools

| Tool | Description |
|------|-------------|
| `generate_image` | Render HTML, fill templates, or AI-generate from natural language prompt |
| `screenshot_url` | Take webpage screenshots |
| `list_templates` | Browse community templates by platform and category |
| `get_template` | Get template variable schema |
| `create_template` | Save a design as reusable template (private draft) |

## Platform Presets

| Platform | Size | Use |
|----------|------|-----|
| `xiaohongshu` | 1080x1440 | Notes, product cards |
| `xiaohongshu_wide` | 1080x810 | Wide format notes |
| `instagram_post` | 1080x1080 | Feed posts |
| `instagram_story` | 1080x1920 | Stories, reels covers |
| `twitter_card` | 1200x628 | Link preview cards |
| `twitter_post` | 1200x675 | Image posts |
| `linkedin_post` | 1200x627 | Professional posts |
| `youtube_thumb` | 1280x720 | Video thumbnails |
| `wechat_cover` | 900x383 | Article covers |
| `wechat_thumb` | 200x200 | Article thumbnails |
| `og_image` | 1200x630 | Open Graph images |
| `custom` | 1080x1080 | Any custom size |

## Contributing

PRs welcome! To add a new platform skill:

1. Create `skills/<platform>/SKILL.md` with frontmatter
2. Add `references/algorithm.md` — platform-specific content strategy
3. Add `references/design-style.md` — visual design guide
4. Add `references/templates.md` — recommended templates and prompt examples

## License

MIT
