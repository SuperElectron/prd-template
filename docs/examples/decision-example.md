# Decision: Use Markdown PRDs in Git Over Google Docs

**Date:** 2024-03-01

**Status:** Accepted

**Deciders:** @productlead, @ctolead

## Context

The team has been writing PRDs in Google Docs. Review happens via comments, but there's no version history tied to implementation, docs get lost in Drive, and there's no clear "approved" state.

## Decision

Move PRDs to a dedicated Git repository using markdown files. Reviews happen via pull requests. Approval = merge to main.

## Consequences

**Benefits:**
- PRDs live next to the work they describe (or can be linked via issues)
- PR review gives structured approval workflow with audit trail
- Version history is automatic and tied to specific changes
- Markdown is portable, searchable, and diff-friendly

**Trade-offs:**
- Less rich formatting than Google Docs (no inline images without hosting)
- Team members less familiar with Git will need onboarding
- Real-time collaboration requires branch coordination rather than simultaneous editing

## Alternatives Considered

- **Notion** — Good UX but poor Git integration and export limitations
- **Confluence** — Too heavyweight for small teams, search is weak
- **Google Docs** — Status quo, rejected due to review and versioning gaps
