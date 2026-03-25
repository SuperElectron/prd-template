# PRD Template

A structured workspace for Product Requirement Documents — powered by [Claude Code](https://claude.ai/code).

## TL;DR

- download and start

```bash
curl -fsSL https://claude.ai/install.sh | bash        # 1. install claude
git clone https://github.com/YOUR_ORG/prd-template.git && cd prd-template
claude                                                  # 2. start claude
```

Then type:

```
/guide
```

That's it. Claude will walk you through setup, explain the workflow, and help you write your first PRD.

---

## Commands

| Command | What It Does |
|---|---|
| `/guide` | **Start here.** Shows setup, workflow, and all available commands |
| `/new-prd` | Create a new PRD from the template |
| `/new-decision` | Create a new decision record |
| `/new-research` | Create a research brief (with web research) |
| `/review-prd` | Review a PRD for completeness and quality |
| `/jtbd-analysis` | Analyze a PRD using the Jobs-to-be-Done framework |

---

## Folder Structure

```
prd-template/
├── prds/                              # Active PRDs — one file per feature/initiative
├── decisions/                         # Decision records — key product/tech calls
├── research/                          # Supporting research, analysis, interviews
│
├── docs/                              # Guides, templates, and examples
│   ├── guide.md             # Setup guide
│   ├── workflow.md                    # PRD lifecycle, branches, reviews
│   ├── writing.md              # How to write good PRDs and decisions
│   ├── templates/                     # Document templates (prd, decision, research)
│   └── examples/                      # Filled-in examples to reference
│
├── .github/                           # PR templates, issue templates, CI automation
├── .claude/commands/                  # Slash commands (the table above)
├── CLAUDE.md                          # AI instructions (loaded automatically)
└── .mcp.json                          # MCP server config
```

### What Goes Where

| Folder | Purpose | Naming |
|---|---|---|
| `prds/` | New features and initiatives | `YYYY-MM-DD_short-description.md` |
| `decisions/` | Key choices (build vs buy, tech picks, scope cuts) | `YYYY-MM-DD_short-description.md` |
| `research/` | User interviews, competitive analysis, market data | `YYYY-MM-DD_short-description.md` |

**Bugs and issues** go in [GitHub Issues](../../issues), not in this repo.

---

## Guides

| Guide | What It Covers |
|---|---|
| **[Getting Started](docs/guide.md)** | Prerequisites, API keys, MCP servers |
| **[Workflow](docs/workflow.md)** | Branch naming, PR process, review, merge, PRD lifecycle |
| **[Writing Guide](docs/writing.md)** | How to write effective PRDs and decision records |

---

## GitHub Automation

These run automatically on every pull request:

| Action | What It Does |
|---|---|
| **Markdown Lint** | Checks formatting on all `.md` files |
| **Document Checks** | Enforces `YYYY-MM-DD_short-description.md` naming; warns if PRDs miss required sections |
| **Auto-Label** | Labels PRs as `prd`, `decision`, `research`, or `docs` |

Naming convention is enforced. Structure checks are **warnings only**.

---

## License

MIT — Use this template however you like.
