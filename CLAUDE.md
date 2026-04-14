# CLAUDE.md

## Project Overview

Open-source AI agent skills for [Rendshot](https://rendshot.com) — an image generation and screenshot API. This repo teaches AI agents how to use Rendshot effectively, with platform-specific content strategy and design guidance.

**Repo**: `RendShotTeam/rendshot-skills` (public)
**Related**: `RendShotTeam/rendshot` (private monorepo — the product itself)

## Structure

```
skills/
├── rendshot/          — Core tool usage (MCP, API, CLI, SDK)
├── xiaohongshu/       — Xiaohongshu content strategy + design
└── instagram/         — Instagram content strategy + design
integrations/
├── claude-code/       — .mcp.json for Claude Code plugin
├── cursor/            — .cursorrules
└── codex/             — Setup instructions
```

Each skill follows the same pattern:
- `SKILL.md` — Frontmatter (name + description for triggering) + workflow instructions
- `references/` — Progressive disclosure: algorithm, design-style, templates

## Conventions

### Skill Format

- **Frontmatter `description`** must include all trigger words and scenarios. This is the ONLY place trigger logic lives — never put "When to use" sections in the body.
- **SKILL.md body** stays under 150 lines. Delegate details to `references/`.
- **References** are loaded by the AI only when needed (progressive disclosure).
- Use imperative voice throughout.

### Content Accuracy

- **MCP tool parameters** must match the source code in `RendShotTeam/rendshot/packages/mcp/src/tools/*.ts`. When the product API changes, update `skills/rendshot/references/mcp-tools.md` and `api-endpoints.md` accordingly.
- **Platform presets** must match `packages/api/src/routes/aiRender.ts` in the main repo. Currently 12 presets.
- **Return types** must include all fields from the SDK types (`@rendshot/sdk`).

### Platform Skills (xiaohongshu, instagram, etc.)

Each platform skill has three reference files:
1. `algorithm.md` — Platform recommendation mechanics, content strategy, audience targeting
2. `design-style.md` — Visual styles, color palettes by niche, typography, layout patterns
3. `templates.md` — Recommended templates (search queries) + AI prompt examples

When adding a new platform:
1. Copy an existing platform skill as template
2. Follow the same 5-step workflow: Understand → Algorithm → Style → Generate → Save
3. Keep Rendshot tool calls consistent with `skills/rendshot/`

### Cross-Platform Consistency

- All platform skills use the same 5-step workflow structure
- Rendshot tool call syntax must be identical across all skills
- Platform preset names and dimensions must match across all files (SKILL.md, README, .cursorrules)

## Commands

```bash
# Validate a skill (from skill-creator)
python3 ~/.claude/skills/skill-creator/scripts/quick_validate.py skills/xiaohongshu

# Package a skill
python3 ~/.claude/skills/skill-creator/scripts/package_skill.py skills/xiaohongshu
```

No build step. No dependencies. This is a content-only repo.

## Adding New Skills

1. Initialize: `python3 ~/.claude/skills/skill-creator/scripts/init_skill.py <name> --path skills`
2. Clean up generated example files (scripts/, assets/)
3. Write SKILL.md + references following existing patterns
4. Verify tool parameters against the main rendshot repo
5. Update README.md platform presets table if adding a new platform
6. Run validation before committing
