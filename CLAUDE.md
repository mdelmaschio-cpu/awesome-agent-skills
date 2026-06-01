# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

A curated list of Agent Skills for AI coding assistants — maintained at
[github.com/VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills). It is a **pure
Markdown repository** with no runnable source code, no build system, and no test suite. The only substantive
file is `README.md`; everything else is supporting documentation or git metadata.

Skills are links to external repositories. None of the skills themselves live here — this repo only catalogs
them.

Current scale: **1,100+ skills** across 50+ official teams and numerous community contributors.

---

## Directory Structure

```
awesome-agent-skills/
├── README.md          # The entire curated list — the only file that changes regularly
├── CLAUDE.md          # This file
├── CONTRIBUTING.md    # Contributor guidelines (entry format, placement rules, PR titles)
├── LICENSE            # MIT
└── .gitignore         # Ignores: skills/, scripts/__pycache__/, .DS_Store, .claude/
```

The `.gitignore` reveals two directories that may exist locally but are not committed:
- `skills/downloads/` — a local cache for downloaded skill files
- `scripts/__pycache__/` — Python bytecode from any local tooling

---

## README.md Structure

`README.md` is the heart of the repository. It is organized into two top-level sections:

### 1. Official Skills

Skills published by named development teams. Each team gets its own `### Skills by <Team>` heading. Many
sections use `<details open>` or `<details>` collapsible blocks:

```html
<details open>
<summary><h3 style="display:inline">Skills by Vercel Engineering Team</h3></summary>
- **[vercel-labs/skill-name](URL)** - Short description
</details>
```

Teams currently listed include: Anthropic (Official Claude Skills), VoltAgent, Angular, Composio, Supabase,
Google Gemini, Stripe, Courier, CallStack, Expo, Better Auth, Tinybird, HashiCorp (Terraform), Sanity,
Firecrawl, Neon, ClickHouse, Remotion, Replicate, Typefully, Venice.ai, Vercel, Cloudflare, Netlify, Google
Labs (Stitch), Google Workspace CLI, Hugging Face, Trail of Bits, Sentry, Microsoft (133 skills, 6
languages), fal.ai, WordPress, OpenAI, Figma, Corey Haines (Marketing), Kim Barrett (Advertising), Binance,
Dean Peters (Product Management), Paweł Huryn (Product Management), MiniMax, DuckDB, GSAP, Garry Tan
(gstack), Notion, Resend, Addy Osmani (Web Quality), MongoDB, Apollo GraphQL, Auth0, Brave, Browserbase,
CodeRabbit, Coinbase, Datadog Labs, Firebase, Flutter, Redis, and Venice.ai.

### 2. Community Skills

Skills from individual contributors, grouped into subcategories:

| Subcategory | Examples of what's covered |
|---|---|
| **Vector Databases** | Qdrant |
| **Marketing** | Cold email, SEO, social content, ad creative |
| **Productivity and Collaboration** | Notion, PPT generation, WhatsApp, Linear |
| **Development and Testing** | Rails, Terraform, AWS, Playwright, Swift, security |
| **Context Engineering** | Memory systems, multi-agent patterns, context compression |
| **AI and Data** | ML research, image generation, LLM evaluation |
| **n8n Automation** | JavaScript/Python code nodes, workflow patterns |
| **Other** | General-purpose community skills |
| **Specialized Domains** | Legal, genealogy, electronics, materials science, VMware |

### 3. Closing Sections

- **Security Notice** — skills are curated, not audited; links to Snyk Skill Scanner and Agent Trust Hub
- **Skills Paths for Other AI Coding Assistants** — table mapping each tool to its project and global path
- **Skill Quality Standards** — quality criteria table for entries
- **Contributing** — link to CONTRIBUTING.md

---

## Key Files and Their Roles

| File | Role |
|---|---|
| `README.md` | The entire curated list — 1,500+ lines, ~55K tokens |
| `CONTRIBUTING.md` | Entry format, placement rules, PR title format, acceptance criteria |
| `CLAUDE.md` | AI assistant guidance (this file) |
| `LICENSE` | MIT |

---

## Adding a Skill Entry

Every entry follows this **exact** format:

```markdown
- **[author/skill-name](https://github.com/author/repo/path)** - Short description of what it does
```

### Rules

- Description must be **10 words or fewer** — no lengthy paragraphs
- Link must point to a **public repository** that has documentation (README or SKILL.md)
- Name must include an **author/org prefix** (e.g., `stripe/upgrade-stripe`, not just `upgrade-stripe`)
- **Placement**: append to the end of the matching team section or community subcategory; use "Other" if
  no category fits
- **PR title format**: `Add skill: author/skill-name`
- Skills must have **real community usage** — brand-new skills are not accepted; let them mature first

### URL Patterns

Most official skills now use the `officialskills.sh` CDN pattern:
```
https://officialskills.sh/<org>/skills/<skill-name>
```
Some older or community entries still use direct GitHub URLs:
```
https://github.com/<org>/<repo>/tree/main/skills/<skill-name>
```
Both are valid. When adding new official team skills, prefer `officialskills.sh` if the team uses it.

---

## Development Workflow

There is **no build step, no linter, and no test runner**. The entire workflow is:

1. Edit `README.md`
2. Open a PR with the title `Add skill: author/skill-name`
3. Pass human review

**To verify your entry before submitting:**
- Confirm the link is accessible (public repo, not 404)
- Count the description words (≤10)
- Confirm the author/org prefix is in the name
- Check that the skill has documentation (README or SKILL.md in the linked repo)

---

## Skill Quality Standards

| Area | Guideline |
|------|-----------|
| **Description** | Third person. State *what* it does and *when* to use it. Use specific keywords (e.g., "PostgreSQL migration" not "database stuff"). |
| **Progressive disclosure** | Top-level metadata under ~100 tokens. Skill body below 500 lines. Load large docs on demand, not inline. |
| **No absolute paths** | Never hard-code machine-specific paths. Use relative paths or `$HOME`/`$PROJECT_ROOT`. |
| **Scoped tools** | Declare only the tools the skill actually needs. Avoid `"tools": ["*"]`. |

---

## Skill Installation Paths by Tool

Skills are installed in tool-specific directories. For reference when users ask how to install a skill:

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

---

## Notes for AI Assistants

- **Do not add skills without real community usage.** This is the most common rejection reason.
- **Do not create new sections or subcategories** unless clearly warranted; use "Other" when in doubt.
- **The README is append-only for entries.** New skills go at the end of their section, not interleaved.
- **Description word count matters.** Count words before submitting; reviewers enforce the ≤10 word rule.
- **`<details>` blocks**: some team sections use `<details open>` (expanded by default) and some use
  `<details>` (collapsed). Match the pattern of the surrounding team sections when adding to an existing
  section. New team sections typically use `<details open>`.
- **Do not edit any file other than `README.md`** in normal contribution workflows. `CLAUDE.md`,
  `CONTRIBUTING.md`, and `LICENSE` are maintained separately.
- **The Table of Contents** at the top of `README.md` uses anchor links. If you add a new `### Skills by
  <Team>` heading, you must also add a corresponding entry to the ToC table.
- **Security**: skills are curated but not security-audited. Do not assert that a listed skill is safe;
  always direct users to review the source themselves.
- **Skill count badge**: the README header shows `Skills-1100+-blue`. Update this badge when the count
  meaningfully crosses a new threshold (e.g., 1200+), but only do so when the actual count warrants it.
