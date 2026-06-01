# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

This is a curated list of Agent Skills for AI coding assistants — a pure Markdown repository with no runnable code, no build system, and no test suite. All content lives in `README.md`. Skills are links to external repositories; none of the skills themselves live here.

## No Build or Test Commands

There are no build, lint, or test commands. The only "development" work is editing `README.md` to add or update skill entries.

## README Structure

`README.md` is organized into two major sections:

1. **Official Skills** — skills published by named development teams (Anthropic, Vercel, Stripe, Cloudflare, etc.), each under their own `### Skills by <Team>` heading. Many use `<details>` blocks.
2. **Community Skills** — skills from individual contributors, grouped into subcategories: Marketing, Productivity and Collaboration, Development and Testing, Context Engineering, AI and Data, n8n Automation, Other, and Specialized Domains.

The file ends with a **Skill Quality Standards** table, a **Skills Paths** table (showing where each AI tool looks for skills), and a **Security Notice**.

## Adding a Skill Entry

Every entry follows this exact format:

```markdown
- **[author/skill-name](https://github.com/author/repo/path)** - Short description of what it does
```

Rules enforced during review:
- Description must be **10 words or fewer** — no lengthy paragraphs
- Link must point to a **public repository** that has documentation (README or SKILL.md)
- Name must include an **author/org prefix**
- **Placement**: add to the end of the matching team section or community subcategory; use "Other" if no category fits
- **PR title format**: `Add skill: author/skill-name`
- Skills must have **real community usage** — brand-new skills are not accepted

## Skill Quality Standards (for entries you add)

| Area | Guideline |
|------|-----------|
| **Description** | Third person. State *what* it does and *when* to use it. Use specific keywords (e.g., "PostgreSQL migration" not "database stuff"). |
| **Progressive disclosure** | Top-level metadata under ~100 tokens. Skill body below 500 lines. Load large docs on demand, not inline. |
| **No absolute paths** | Never hard-code machine-specific paths. Use relative paths or `$HOME`/`$PROJECT_ROOT`. |
| **Scoped tools** | Declare only the tools the skill actually needs. Avoid `"tools": ["*"]`. |

## AI Assistant Guidance

When working in this repository:
- **Do not add skill entries** for repos without demonstrated community usage — the list requires real-world adoption, not brand-new skills
- **PR title must be** `Add skill: author/skill-name` (no other format accepted)
- **One entry per PR** — batch submissions are rejected
- **Check for duplicates** before adding: search the README; similar skills may already be listed under a different name
- **Description must be 10 words or fewer** — anything longer will be flagged during review
- **No promotional language** — descriptions are factual ("Runs PostgreSQL migrations"), not marketing ("The best migration tool")
- **Pure Markdown repo**: do not introduce scripts, configs, or build tooling

## Skill Paths by Tool

Skills are installed in tool-specific directories. For reference:

| Tool | Project Path | Global Path |
|------|-------------|-------------|
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |
| Gemini CLI | `.gemini/skills/` | `~/.gemini/skills/` |
| Cursor | `.cursor/skills/` | `~/.cursor/skills/` |
| GitHub Copilot | `.github/skills/` | `~/.copilot/skills/` |
| Codex | `.agents/skills/` | `~/.agents/skills/` |
| Windsurf | `.windsurf/skills/` | `~/.codeium/windsurf/skills/` |
| OpenCode | `.opencode/skills/` | `~/.config/opencode/skills/` |
| Antigravity | `.agent/skills/` | `~/.gemini/antigravity/skills/` |
