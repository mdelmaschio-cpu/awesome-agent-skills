# awesome-agent-skills

A curated "awesome list" of Agent Skills for AI coding assistants — hand-picked, not AI-slop generated. This is a pure Markdown repository: no runnable code, no build system, no test suite.

## Project Overview

This repository curates links to real-world Agent Skills created and used by actual engineering teams and community contributors. It does **not** host skill files directly — each skill lives in its own external repository. This list simply organizes and surfaces the best ones.

**Scope:** Skills compatible with Claude Code, Codex, Antigravity, Gemini CLI, Cursor, GitHub Copilot, OpenCode, Windsurf, and other AI coding assistants.

**Scale:** 1,100+ skills curated as of the last update.

**Origin project:** [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) — this fork is maintained by mdelmaschio-cpu.

## What Is an Agent Skill?

An Agent Skill is a markdown file that gives an AI coding assistant structured guidance for a specific task type. Skills tell the model *how* to approach a class of problem, not *what* the answer is.

Skills are discovered and invoked by matching the skill's description (and sometimes its body) against the user's request. The better the description, the more reliably the skill is selected.

**Key characteristics of a good skill:**
- Focused on one specific task type or domain
- Has a short, precise description rich with trigger phrases
- Provides actionable guidance the model can follow step-by-step
- Has real community adoption (not brand-new)
- Lives in a public repository with documentation (README or SKILL.md)

## Repository Structure

```
awesome-agent-skills/
├── README.md          # The main curated list (very large — ~180KB)
├── CLAUDE.md          # This file — AI assistant guidance
├── CONTRIBUTING.md    # How to add a skill entry
└── LICENSE
```

All content is in `README.md`. There are no subdirectories, no skill files, and no code.

## README.md Organization

The README is organized into two major sections:

### 1. Official Skills

Skills published by named development teams, each under a `### Skills by <Team>` heading. Many use `<details>` blocks for collapsible content. Teams with official sections include:

- Anthropic (Claude), VoltAgent, Angular, Composio, Supabase, Google Gemini, Stripe, Courier, CallStack, Expo, Better Auth, Tinybird, HashiCorp (Terraform), Sanity, Firecrawl, Neon, ClickHouse, Remotion, Replicate, Typefully, Vercel, Cloudflare, Netlify, Google Labs (Stitch), Google Workspace CLI, Hugging Face, Trail of Bits, Sentry, Microsoft, fal.ai, WordPress, OpenAI, Figma, Corey Haines (Marketing), Binance, Dean Peters (Product Manager), Paweł Huryn (Product Management), MiniMax, DuckDB, GSAP (GreenSock), Garry Tan (gstack), Notion, Resend, Addy Osmani (Web Quality), MongoDB, Kim Barrett (Advertising), Apollo GraphQL, Auth0, Brave, Browserbase, CodeRabbit, Coinbase, Datadog Labs, Firebase, Flutter, Venice.ai, Redis, and more.

### 2. Community Skills

Skills from individual contributors, grouped into subcategories:

- **Marketing** — copywriting, SEO, campaign management
- **Productivity and Collaboration** — workflow automation, team tools
- **Development and Testing** — code quality, CI/CD, debugging
- **Context Engineering** — prompt design, memory, retrieval
- **AI and Data** — ML pipelines, data analysis, model management
- **n8n Automation** — workflow automation with n8n
- **Other** — skills that don't fit existing subcategories
- **Specialized Domains** — niche verticals (legal, finance, healthcare, etc.)

### 3. Reference Tables

At the end of the README:

- **Skill Quality Standards** — guidelines for what makes a skill entry acceptable
- **Skills Paths** — where each AI tool looks for skills (project-level and global paths)
- **Security Notice** — warnings about skill security and trust

## Skill Entry Format

Every entry in README.md follows this exact format:

```markdown
- **[author/skill-name](https://github.com/author/repo/path)** - Short description of what it does
```

**Format rules:**
- Description is **10 words or fewer** — no lengthy paragraphs
- Link points to a **public repository** with documentation
- Name includes an **author/org prefix** (e.g. `anthropics/docx`, not just `docx`)
- Entry is placed at the **end** of the matching section or subcategory
- Use the "Other" subcategory when no category fits

## Skill Paths by Tool

For reference, where each AI coding tool installs skills:

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

## How to Contribute

### Adding a Skill Entry

1. Find the right section in `README.md`:
   - If the skill's team already has a section, add to the end of that section.
   - If it's a community skill, add to the end of the matching subcategory.
   - If no category fits, add to "Other".
2. Format the entry exactly as shown above.
3. Verify the link is live and the repo has documentation.
4. Open a PR with title: `Add skill: author/skill-name`

### Requirements for Acceptance

| Requirement | Detail |
|-------------|--------|
| Public repository | Must be publicly accessible |
| Has documentation | README or SKILL.md must exist in the linked repo |
| Author/org prefix | Name must include who made it |
| Short description | 10 words or fewer |
| Real community usage | Brand-new skills are not accepted — let it mature first |
| Working link | Verify the URL resolves before submitting |

### PR Title Format

`Add skill: author/skill-name`

## Skill Quality Standards (for Entries You Add)

| Area | Guideline |
|------|-----------|
| **Description** | Third person. State *what* it does and *when* to use it. Use specific keywords (e.g., "PostgreSQL migration" not "database stuff"). |
| **Progressive disclosure** | Top-level metadata under ~100 tokens. Skill body below 500 lines. Load large docs on demand, not inline. |
| **No absolute paths** | Never hard-code machine-specific paths. Use relative paths or `$HOME`/`$PROJECT_ROOT`. |
| **Scoped tools** | Declare only the tools the skill actually needs. Avoid `"tools": ["*"]`. |

## Development Conventions

- **This is a pure Markdown repository.** Do not introduce code, scripts, build tools, or CI configuration unless explicitly requested.
- **All real content is in `README.md`.** Do not create additional skill files or subdirectories here.
- **Do not bulk-add entries.** Each skill entry should represent a real, tested, community-adopted skill.
- **Do not edit formatting of existing entries** without a specific reason — the consistent format is intentional.
- **Preserve `<details>` blocks** in the Official Skills sections — they are used intentionally for collapsible content.
- **The README is large (~180KB).** When searching for a specific section, use anchor links from the Table of Contents rather than scanning the whole file.
- **Links are to external repos** — do not copy skill content into this repository.
- **When adding multiple skills from the same team,** group them under the existing team heading rather than creating duplicate headings.

## How AI Assistants Should Behave in This Repository

- **Only edit `README.md`** when adding or updating skill entries.
- **Use the exact entry format** — do not deviate from the `- **[author/skill-name](url)** - description` pattern.
- **Respect the 10-word description limit** — if a description is longer, trim it.
- **Do not create new files** unless explicitly asked.
- **Do not introduce build tooling, tests, or scripts** — this is intentionally a no-build repository.
- **Check for duplicates** before adding an entry — search `README.md` for the skill name.
- **Place entries correctly** — end of the relevant section, not at the top or in a random location.
- **PR titles must follow the format** `Add skill: author/skill-name` — do not use other formats.
- **Do not accept brand-new skills** into the list — community adoption is a hard requirement.
