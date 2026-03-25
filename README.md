# PRD Template

A template repository for writing Product Requirement Documents (PRDs) — designed for teams where the Chief of Product and Chief of Technology collaborate to document client needs, technical direction, and product strategy.

This is **not a code repo**. It's a structured workspace for product requirements, powered by AI-assisted writing and review via [Claude Code](https://claude.ai/code).

---

## Quick Start

1. **Clone** — `git clone https://github.com/YOUR_ORG/prd-template.git && cd prd-template`
2. **Set up API keys** — `cp .claude/settings.local.json.example .claude/settings.local.json` and paste your tokens
3. **Start Claude** — `claude`

Full setup instructions: **[docs/getting-started.md](docs/getting-started.md)**

---

## Folder Structure

```
prd-template/
├── README.md                          # You are here
├── CLAUDE.md                          # AI instructions (loaded automatically by Claude Code)
├── .mcp.json                          # MCP server config (uses ${VAR} from settings.local.json)
├── .claude/settings.local.json        # Your API keys (gitignored)
│
├── docs/                              # How to use this repo
│   ├── getting-started.md             # Setup guide
│   ├── workflow.md                    # PRD lifecycle, branches, reviews
│   ├── writing-guide.md              # How to write good PRDs and decisions
│   ├── templates/
│   │   ├── prd-template.md             # PRD template (Jobs-to-be-Done + Lenny's 1-pager)
│   │   ├── decision-template.md       # Decision record template
│   │   └── research-template.md       # Research brief template
│   └── examples/
│       ├── prd-example.md             # A filled-in PRD to reference
│       └── decision-example.md        # A filled-in decision record
│
├── prds/                              # Active PRDs — one file per feature/initiative
├── decisions/                         # Decision records — key product/tech calls
├── research/                          # Supporting research, analysis, interviews
│
└── .github/                           # PR templates, issue templates, automation
    ├── CODEOWNERS
    ├── pull_request_template.md
    ├── ISSUE_TEMPLATE/
    └── workflows/
```

### What Goes Where

| Folder | Purpose | Example |
|---|---|---|
| `prds/` | New features and initiatives | `prds/2024-06-15_payment-integration.md` |
| `decisions/` | Key choices (build vs buy, tech picks, scope cuts) | `decisions/2024-03-01_auth-approach.md` |
| `research/` | User interviews, competitive analysis, market data | `research/2024-05-10_competitor-analysis.md` |
| `docs/` | How to use this repo (guides, templates, examples) | Don't modify unless you're changing the process |

**Bugs and issues** go in [GitHub Issues](../../issues), not in this repo. Use the issue templates to report bugs or request new PRDs.

---

## Guides

| Guide | What It Covers |
|---|---|
| **[Getting Started](docs/getting-started.md)** | Install Claude Code, set up MCP servers, write your first PRD |
| **[Workflow](docs/workflow.md)** | Branch naming, PR process, review checklist, merge rules |
| **[Writing Guide](docs/writing-guide.md)** | How to write effective PRDs and decision records |

---

## Working with Claude Code

This repo includes a `CLAUDE.md` file that automatically configures Claude as a senior product strategist when you run `claude` in this directory.

### Useful Commands (with [ECC](https://github.com/affaan-m/everything-claude-code) installed)

| Command | Use Case |
|---|---|
| `/plan "feature description"` | Plan out a PRD structure before writing |
| `/deep-research "topic"` | Research competitors, market, or technical feasibility |
| `/code-review` | Review a PRD for completeness (works on markdown too) |
| `/article-writing` | Draft polished, well-structured content |

### Example Prompts

```
> Help me write a PRD for [feature name]. The problem is [description].
> Review the PRD in prds/my-feature.md — is it ready for engineering?
> Research how competitors handle [topic]. Summarize the patterns.
```

---

## GitHub Automation

This repo includes GitHub Actions that run on every pull request:

| Action | What It Does |
|---|---|
| **Markdown Lint** | Checks formatting on all `.md` files |
| **PRD Structure Check** | Warns if PRDs in `prds/` are missing required sections (Context, Job Stories, Metrics, Scope) |
| **Auto-Label** | Labels PRs as `prd`, `decision`, `research`, or `docs` based on which files changed |

All checks produce **warnings only** — they will never block a merge.

---

## License

MIT — Use this template however you like.
