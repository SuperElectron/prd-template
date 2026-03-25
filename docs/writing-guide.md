# Writing Guide

How to write effective PRDs and decision records in this repo.

---

## Examples

Before writing your first PRD or decision record, read the examples:

- **[PRD Example](./examples/prd-example.md)** — A complete PRD for a notification preferences feature
- **[Decision Example](./examples/decision-example.md)** — A decision record for choosing markdown over Google Docs

These show what "done" looks like.

---

## Writing a PRD

### Start With the Problem

Every PRD begins with **why** — not what you want to build. If you can't explain the problem in 2-3 sentences, you don't understand it well enough yet. Ask yourself:

- What specific pain point are we solving?
- Why solve this now? What happens if we don't?

### Write Job Stories, Not User Stories

We use the **Jobs-to-be-Done** format instead of traditional user stories:

> When **[situation]**, I want to **[motivation]**, so I can **[expected outcome]**.

**Good:** When I receive a marketing email I don't care about, I want to turn off that specific category, so I can stay subscribed to updates that matter to me.

**Bad:** As a user, I want notification preferences.

The difference: job stories describe the *situation* and *outcome*, not just the feature. They give engineers context for *why* something matters.

### Make Metrics Measurable

If you can't put a number on it, push harder.

- **Good:** Reduce email unsubscribe rate from 4.2% to below 2% within 90 days.
- **Bad:** Improve user retention.

Every PRD needs:
- **A North Star metric** — the primary thing you're trying to move
- **A Guardrail metric** — something that should NOT get worse as a side effect

### Be Explicit About Scope

The "Out-of-Scope" section is as important as the "In-Scope" section. It prevents scope creep and sets expectations. If someone might assume it's included, call it out.

### Keep It Short

If your PRD is longer than 2 pages, it's probably two PRDs. Split it.

---

## Writing a Decision Record

Decision records capture *why* a choice was made so future team members don't re-litigate it. Write one when:

- You're choosing between multiple valid approaches
- The decision is hard to reverse
- Multiple stakeholders have input
- Someone in 6 months will ask "why did we do it this way?"

Keep them brief: context (what prompted the decision), the decision itself, consequences (benefits AND trade-offs), and alternatives you rejected.

---

## Writing Style

- **Clear, direct language** — no jargon unless it's domain-specific and defined
- **Short paragraphs and bullet points** over walls of text
- **Present tense, active voice** — "Users receive" not "Users will be receiving"
- **Specific over vague** — "reduce page load time by 200ms" not "make it faster"
- **No hedging** — "This will reduce churn" not "This should hopefully help with churn"

---

## Checklist Before Submitting for Review

### PRD
- [ ] Problem statement is clear — a new team member would understand it
- [ ] Job stories are specific enough that an engineer could build from them
- [ ] Functional requirements are testable
- [ ] Success metrics have specific numbers
- [ ] Out-of-scope section exists and is honest
- [ ] Risks are acknowledged
- [ ] Status is set to "In-Review"
- [ ] File is named `YYYY-MM-DD_short-description.md` in `prds/`

### Decision Record
- [ ] Context explains the situation clearly
- [ ] Decision is stated in one paragraph
- [ ] Alternatives considered are listed with reasons for rejection
- [ ] Consequences include both benefits AND trade-offs
