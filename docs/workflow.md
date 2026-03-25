# Workflow

How documents move through this repo — from draft to approved and beyond.

---

## PRD Lifecycle

```
1. Branch    →    2. Write    →    3. PR    →    4. Review    →    5. Merge
```

### 1. Create a Branch

```bash
git checkout -b prd/short-description
```

Branch naming:
- `prd/short-description` — new PRDs
- `review/short-description` — revisions to existing PRDs
- `decision/short-description` — decision records
- `research/short-description` — research documents

### 2. Write the Document

Copy the appropriate template from `docs/templates/`:

```bash
# For a PRD
cp docs/templates/prd-template.md prds/2024-03-15_my-feature.md

# For a decision record
cp docs/templates/decision-template.md decisions/2024-03-15_my-decision.md
```

**File naming:** `YYYY-MM-DD_short-description.md` (e.g., `2024-03-15_notification-preferences.md`)

This applies to all document types — PRDs, decisions, and research. The date prefix keeps documents sorted chronologically in the folder.

Set the **Status** field to `Draft` while writing.

### 3. Open a Pull Request

```bash
git add prds/2024-03-15_my-feature.md
git commit -m "my-feature: initial draft"
git push -u origin prd/my-feature
```

Open a PR on GitHub. The PR template will guide you through a checklist.

Update the **Status** field to `In-Review`.

### 4. Review

PRDs are reviewed by product and engineering together. Reviewers should check:

- Is the problem clearly stated?
- Are job stories specific enough to build from?
- Are success metrics measurable with existing tooling?
- Is the scope realistic?
- Are risks acknowledged honestly?

Use GitHub's review features — line comments for specific feedback, "Request changes" for blocking issues, "Approve" when ready.

### 5. Merge

Once approved, update the **Status** field to `Approved` and merge to main. Use squash merge to keep history clean.

---

## After Approval: PRD Lifecycle

PRDs don't disappear after merge. They're a living record. Update the **Status** field as the work progresses:

| Status | Meaning | When to Set |
|---|---|---|
| `Draft` | Work in progress | While writing |
| `In-Review` | Open for feedback | When PR is opened |
| `Approved` | Accepted as the plan | When PR is merged |
| `Implemented` | Engineering has shipped it | When the feature is live. Link to the release or implementation PR. |
| `Superseded` | Replaced by a newer PRD | When a new PRD covers this scope. Add a note: "Superseded by `prds/YYYY-MM-DD_new-prd.md`" |
| `Archived` | No longer relevant | When the feature is deprecated or the initiative was cancelled. Add a brief note explaining why. |

**The `prds/` folder is your product history.** A year from now, a new team member can read through it and understand every product decision that was made and why.

---

## For Startups and Small Teams

You don't need the full ceremony. The minimum viable process:

1. **Write** — Copy the template, fill it in. The value is forcing yourself to think through the problem, scope, and metrics before writing code.
2. **Review** — Get one other person to read it. Even a quick "looks good" catches blind spots.
3. **Merge** — That's it. Skip CODEOWNERS, skip branch protection, skip labels. Add those when you grow.

The template is the product. The process is optional.

---

## Commit Messages

Start with the document name:

```
notification-preferences: initial draft
notification-preferences: add success metrics
notification-preferences: address review feedback
auth-middleware: decision record for token storage approach
```

---

## When to Write What

| Situation | Document Type | Where |
|---|---|---|
| New feature or initiative | PRD | `prds/` |
| Significant change to existing feature | PRD | `prds/` |
| Choosing between approaches (build vs buy, tech choice) | Decision Record | `decisions/` |
| User interviews, competitive analysis, market data | Research | `research/` |
| Bug or issue with existing product | GitHub Issue | GitHub Issues tab |

**Rule of thumb:** If it needs cross-functional review and defines *what to build*, it's a PRD. If it captures *why we chose this approach*, it's a decision record. If it's a problem to fix, it's a GitHub Issue.

---

## Branch Protection (Recommended)

Configure these in GitHub repo settings (Settings > Branches > Branch protection rules):

- **Require pull request reviews before merging** — at least 1 reviewer
- **Require status checks to pass** — markdown lint
- **Allow squash merging** — keeps history clean for docs
- **Do NOT require signed commits** — non-technical contributors shouldn't need GPG keys
