# CLAUDE.md — awesome-agent-skills

This file provides guidance to AI assistants working in this repository.

## What This Repository Is

A curated list of **Agent Skills** for AI coding assistants — a pure Markdown repository with no runnable code, no build system, and no test suite. All content lives in `README.md`. Skills are links to external repositories; none of the skills themselves live here.

## No Build or Test Commands

There are no build, lint, or test commands. The only "development" work is editing `README.md` to add or update skill entries.

## README Structure

`README.md` is organized into two major sections:

1. **Official Skills** — skills published by named development teams (Anthropic, Vercel, Stripe, Cloudflare, etc.), each under their own `### Skills by <Team>` heading. Many use `<details>` blocks.
2. **Community Skills** — skills from individual contributors, grouped into subcategories:
   - Marketing
   - Productivity and Collaboration
   - Development and Testing
   - Context Engineering
   - AI and Data
   - n8n Automation
   - Other
   - Specialized Domains

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

## What Agent Skills Are

Claude Agent Skills are reusable instruction packages installed in AI coding tools. Each skill is a folder containing a `SKILL.md` file with YAML frontmatter (`name`, `description`) and Markdown instructions, optionally bundled with scripts, references, and assets.

Skills load **progressively**:
- At session start: the agent sees only `name` + `description` (~100 tokens per skill)
- When relevant: full `SKILL.md` body loads (~5,000 tokens max)
- On demand: `scripts/`, `references/` files load only when needed

This lets a single agent host hundreds of skills without bloating its context window.

**Skills vs MCP vs Tools:**
- **MCP** — how agents connect to external systems (auth, transport, discovery)
- **Tools** — individual functions agents invoke
- **Skills** — workflows: what to do, in what order, with what guardrails

## Skill Quality Standards (for entries you add)

| Area | Guideline |
|------|-----------|
| **Description** | Third person. State *what* it does and *when* to use it. Use specific keywords (e.g., "PostgreSQL migration" not "database stuff"). |
| **Progressive disclosure** | Top-level metadata under ~100 tokens. Skill body below 500 lines. Load large docs on demand, not inline. |
| **No absolute paths** | Never hard-code machine-specific paths. Use relative paths or `$HOME`/`$PROJECT_ROOT`. |
| **Scoped tools** | Declare only the tools the skill actually needs. Avoid `"tools": ["*"]`. |
| **No paid-API-only skills** | Skills requiring paid API keys must clearly note this. |
| **Community usage** | Brand-new skills with no usage/stars are not accepted. |

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

## Security Notice

When evaluating skills to add to the list:
- Verify the skill doesn't execute arbitrary code without user confirmation
- Check for prompt injection risks in skill descriptions
- Ensure skills requiring sensitive credentials use environment variables, not hardcoded values
- Skills that call external APIs should document what data is sent and to whom

## Contributing Process

1. Check the existing list for duplicates
2. Verify the skill has real community usage (stars, forks, issues, discussion)
3. Confirm the link points to a public repo with documentation
4. Format the entry as: `- **[author/skill-name](URL)** - Short description ≤10 words`
5. Place at the end of the appropriate section
6. Open a PR with title: `Add skill: author/skill-name`

## Important Notes for AI Assistants

- `README.md` is the only file that matters here — this is a pure curation repo
- Do NOT modify any files in external skill repositories via this repo
- Descriptions must be ≤10 words — this is a hard rule, not a guideline
- Do not add skills that are unmaintained, behind paywalls, or require proprietary access
- The Security Notice at the bottom of README.md must remain — never remove it
- When in doubt about categorization, use "Other" — do not create new top-level categories without maintainer approval
