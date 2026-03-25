# Getting Started

How to set up this repo and start writing PRDs.

---

## Prerequisites

| Tool | Required? | Why | Install |
|---|---|---|---|
| **Git** | Yes | Clone the repo, create branches, open PRs | [git-scm.com](https://git-scm.com) (likely already installed) |
| **Node.js** (v18+) | Yes, if using Claude Code | MCP servers and markdown linting run via `npx` | [nodejs.org](https://nodejs.org) |
| **Claude Code** | Recommended | AI-assisted PRD writing, review, and research | `curl -fsSL https://claude.ai/install.sh \| bash` |

**Without Claude Code:** You only need Git. Copy a template, write in any text editor, open a PR.

**With Claude Code:** Install Node.js first, then Claude Code. Node.js powers the MCP servers (GitHub, web search, memory) and the markdown linter.

---

## 1. Clone the Repo

```bash
git clone https://github.com/YOUR_ORG/prd-template.git my-product-prds
cd my-product-prds
```

---

## 2. Install Claude Code (Optional)

Claude Code is an AI assistant that helps you write, review, and refine PRDs directly from the terminal.

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

See: https://code.claude.com/docs/en/quickstart

---

## 3. Install Everything Claude Code (Optional)

[Everything Claude Code](https://github.com/affaan-m/everything-claude-code) adds 60+ skills and commands. It's optional but gives Claude deep expertise in planning, research, and structured writing.

Open Claude Code and run:

```
/plugin marketplace add affaan-m/everything-claude-code
/plugin install everything-claude-code@everything-claude-code
```

---

## 4. Set Up MCP Servers

MCP servers give Claude access to external tools like GitHub, web search, and persistent memory.

**Copy the example settings file and add your API keys:**

```bash
cp .claude/settings.local.json.example .claude/settings.local.json
```

Get your tokens
- visit github: https://github.com/settings/tokens
- visit exa: https://dashboard.exa.ai/home

Open `.claude/settings.local.json` and paste your keys:

```json
{
  "env": {
    "GITHUB_TOKEN": "ghp_your_real_token_here",
    "EXA_API_KEY": "your_exa_key_here"
  }
}
```

That's it. Claude Code loads these at startup automatically.

### Getting API Keys

| Key | Where to Get It | Required? |
|---|---|---|
| `GITHUB_TOKEN` | [GitHub Personal Access Tokens](https://github.com/settings/tokens) — select `repo` scope | Recommended |
| `EXA_API_KEY` | [exa.ai](https://exa.ai) — sign up for web search API | Optional |

### What the MCP Servers Do

| Server | Purpose |
|---|---|
| **github** | Read/write issues, PRs, and discussions |
| **memory** | Persistent memory across sessions |
| **sequential-thinking** | Better reasoning for complex analysis |
| **context7** | Live documentation lookup |
| **exa-web-search** | Research competitors and market trends |

Servers that need no API key (memory, sequential-thinking, context7) work out of the box.

---

## 5. Start Writing

```bash
claude
```

Ask Claude to help:

```
> Help me write a PRD for [feature name]. The problem is [description].
> Review the PRD in prds/my-feature.md for completeness.
> What's missing from this PRD?
```

Or work without Claude — copy a template and start writing:

```bash
cp docs/templates/prd-template.md prds/2024-03-15_my-feature.md
```

See [Workflow](./workflow.md) for the full process and [Writing Guide](./writing.md) for how to write effective PRDs.
