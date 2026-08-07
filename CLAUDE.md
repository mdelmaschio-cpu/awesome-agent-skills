# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

This is a curated "awesome list" of 1100+ Agent Skills for AI coding assistants — a pure Markdown repository with no runnable code, no build system, and no test suite. All content lives in `README.md` as links to external skill repositories. Skills are maintained by official development teams (Anthropic, Google Gemini, Vercel, Stripe, Cloudflare, and many others) and community contributors. The repository is maintained by the VoltAgent organization.

Skills listed here are compatible with: Claude Code, Codex, Gemini CLI, Cursor, GitHub Copilot, Windsurf, OpenCode, and Antigravity.

**None of the skills themselves live here.** This repo is a curated index of links.

## No Build or Test Commands

There are no build, lint, or test commands. The only "development" work is editing `README.md` to add or update skill entries.

## Repository Structure

```
awesome-agent-skills/
├── README.md          # The entire content: 1100+ skill entries (1500+ lines)
├── CLAUDE.md          # This file — AI assistant guidance
├── CONTRIBUTING.md    # Human-facing contribution guidelines (mirrors these rules)
├── LICENSE            # MIT license
└── .gitignore         # Excludes: skills/, skills/downloads/,
                       #   scripts/__pycache__/, scripts/download-skills.py,
                       #   .DS_Store, .claude/
```

**Note on .gitignore**: `scripts/download-skills.py` is listed in `.gitignore` but does not exist in the committed repository — it was a locally-used helper script that was intentionally excluded. Do not recreate it unless explicitly asked.

## README Structure

`README.md` is organized into two major sections:

### 1. Official Skills

Skills published by named development teams, each under their own `### Skills by <Team>` heading. Approximately 50+ teams are represented. Many team sections use `<details>` collapse blocks when the section is large. Examples include: Anthropic, Google Gemini, Vercel, Stripe, Cloudflare, and many others.

**URL pattern for official team skills**: These typically use `https://officialskills.sh/<org>/skills/<name>` rather than direct GitHub links. Community skills use direct GitHub URLs.

### 2. Community Skills

Skills from individual contributors, grouped into these subcategories in this order:

1. Vector Databases
2. Marketing
3. Productivity and Collaboration
4. Development and Testing
5. Context Engineering
6. Specialized Domains
7. n8n Automation
8. Other

### End-of-file sections

The README ends with:
- **Security Notice** — warns users that listed skills are not audited; review before installing
- **Skills Paths** table — shows where each AI tool looks for skills (project and global paths)
- **Skill Quality Standards** table — criteria for skills being added
- **Contributing** section — links to CONTRIBUTING.md

## Adding a Skill Entry

Every entry follows this exact format:

```markdown
- **[author/skill-name](URL)** - Short description of what it does
```

Rules enforced during review:

- Description must be **10 words or fewer** — no lengthy paragraphs
- Link must point to a **public repository** that has documentation (README or SKILL.md)
- Name must include an **author/org prefix** (e.g. `vercel-labs/react-best-practices`)
- **Placement**: add to the **end** of the matching team section or community subcategory; do not insert in the middle of existing entries; use "Other" if no subcategory fits
- **PR title format**: `Add skill: author/skill-name`
- Skills must have **real community usage** — brand-new skills created recently are not accepted

### Placement decisions

- Official team skill → find or create the `### Skills by <Team>` section in the Official Skills area
- Community skill → append to the end of the correct community subcategory using the order listed above
- No clear fit → append to the "Other" subcategory

### `<details>` blocks

Do not add `<details>` collapse wrappers to sections that are currently not collapsed. Only use them where they already exist, or when creating a very large new team section (10+ entries).

## Skill Quality Standards (for entries you add)

| Area | Guideline |
|------|-----------|
| **Description** | Third person. State *what* it does and *when* to use it. Use specific keywords (e.g., "PostgreSQL migration" not "database stuff"). |
| **Progressive disclosure** | Top-level metadata under ~100 tokens. Skill body below 500 lines. Load large docs on demand, not inline. |
| **No absolute paths** | Never hard-code machine-specific paths. Use relative paths or `$HOME`/`$PROJECT_ROOT`. |
| **Scoped tools** | Declare only the tools the skill actually needs. Avoid `"tools": ["*"]`. |

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

## How AI Assistants Should Work Here

This is a Markdown-only curation project. There is no code to write, build, or test.

**When adding a skill entry:**
1. Confirm the entry follows the exact format: `- **[author/skill-name](URL)** - Short description`
2. Descriptions must be 10 words or fewer, third-person, specific
3. Append to the end of the correct section — do not insert in the middle of existing entries
4. For community skills, use the subcategory order: Vector Databases, Marketing, Productivity and Collaboration, Development and Testing, Context Engineering, Specialized Domains, n8n Automation, Other
5. For official team skills, find or create the `### Skills by <Team>` section within the Official Skills section
6. Official team skill URLs typically use `https://officialskills.sh/<org>/skills/<name>`; community skill URLs point directly to GitHub

**Security context:** Skills listed in this repository are not audited by the maintainers. The README includes a Security Notice section warning users to review all skills carefully before installing them. Do not remove or downplay this warning.

**Do not invent entries.** Only add entries when the user provides a specific skill URL and description to include. Do not fabricate skill names, URLs, or organizations.
