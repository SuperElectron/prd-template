Analyze a PRD using the Jobs-to-be-Done (JTBD) framework.

1. Read the PRD file specified by the user. If no file is specified, list the files in `prds/` and ask which one to analyze.

2. Apply the full JTBD framework to evaluate and strengthen the PRD:

---

## JTBD Framework Reference

Jobs to Be Done (JTBD), developed by Clayton Christensen, reframes product thinking around the progress customers are trying to make in their lives. People don't buy products; they "hire" products to do a job. Understanding the job reveals what you're really competing against and what success looks like.

**Core Principle:** People don't want a quarter-inch drill. They don't even want a quarter-inch hole. They want to hang a picture of their family.

### The Job Formula

```
When I [situation/trigger]
I want to [motivation/progress]
So I can [desired outcome/better state]
```

### Job Dimensions

Every job has multiple dimensions:

| Dimension | Question | Example |
|-----------|----------|---------|
| Functional | What task needs doing? | Track tasks, assign work, see progress |
| Emotional | How do I want to feel? | In control, not overwhelmed, confident |
| Social | How do I want to appear? | Organized, reliable, professional |

### Job Context

Jobs are situation-specific. The same person has different jobs at different times:

```
Morning: "Help me triage what needs attention today"
Deep work: "Get out of my way, let me focus"
End of day: "Help me hand off cleanly so I can disconnect"
```

---

## Analysis Steps

**Step 1: Identify Job Performers**

Who is "hiring" this product? For each performer, identify:
- What they hire the product for
- How frequently they do the job
- What's at stake if the job goes poorly

**Step 2: Identify the Core Job**

- What is the main "job" the user is trying to get done?
- Strip away the solution — what is the underlying goal?
- Express it as: "When I [situation], I want to [motivation], so I can [desired outcome]"
- Go deeper: "They want a drill" → "They want a hole" → "They want to hang a picture" → "They want to enjoy family photos"

**Step 3: Assess Job Dimensions**

For the core job, evaluate all three dimensions:
- **Functional:** What task needs completing?
- **Emotional:** How does the user want to feel during and after?
- **Social:** How does the user want to be perceived?

Does the PRD address only the functional dimension? (Most PRDs do — flag this.)

**Step 4: Map the Job Steps**

Break the core job into discrete stages:
1. **Define** — How does the user recognize the need?
2. **Locate** — How do they find a way to get the job done?
3. **Prepare** — What setup is needed before doing the job?
4. **Confirm** — How do they verify they're ready?
5. **Execute** — The core action of getting the job done
6. **Monitor** — How do they track progress?
7. **Modify** — What adjustments are needed along the way?
8. **Conclude** — How do they finish the job?

**Step 5: Identify Unmet Needs**

For each job step, ask:
- What is the user struggling with today?
- Where is the current solution slow, error-prone, or frustrating?
- What workarounds exist? (Workarounds reveal unmet needs)

Define desired outcomes as:
- **Minimize:** Time spent, errors, frustration, uncertainty
- **Maximize:** Confidence, clarity, speed, awareness

**Step 6: Analyze Competing Solutions**

What else could do this job? Consider:
- **Direct competitors** — Other products solving the same problem
- **Indirect competitors** — Different solutions for the same job (email, spreadsheets, meetings, manual processes)
- **Non-consumption** — Doing nothing, hoping for the best, letting things fall through cracks

Insight: You're often not competing with other tools — you're competing with "just send an email" or "bring it up in standup."

**Step 7: Evaluate the PRD's Job Stories**

- Do the existing job stories map to real job steps?
- Are any job steps missing from the PRD?
- Are the stories solution-focused (bad) or outcome-focused (good)?
- Do they address functional, emotional, AND social dimensions?

**Step 8: Check Functional Requirements Against Jobs**

- Does every functional requirement tie back to a job step?
- Are there requirements that don't serve any job? (scope creep)
- Are there jobs that have no supporting requirement? (gaps)

**Step 9: Evaluate Success Metrics**

- Do metrics measure job completion, not feature usage?
- Good: "Users complete [job] in under 2 minutes"
- Bad: "Users click the new button 500 times/day"
- Are there metrics for the emotional/social dimensions?

---

## Output

3. Output a structured report with:

```markdown
# JTBD Analysis: [PRD Name]

## Job Performers
| Performer | Hires For | Frequency | Stakes |
|-----------|-----------|-----------|--------|

## Core Job Statement
When I [situation], I want to [motivation], so I can [outcome].

The deeper job: [Go one level deeper — what do they really want?]

## Job Dimensions
- **Functional:** [What task]
- **Emotional:** [How they want to feel]
- **Social:** [How they want to appear]
- **PRD coverage:** [Which dimensions are addressed? Which are missing?]

## Job Map
| Step | Sub-jobs | Covered in PRD? | Pain Points |
|------|----------|-----------------|-------------|
| 1. Define | | | |
| 2. Locate | | | |
| 3. Prepare | | | |
| 4. Confirm | | | |
| 5. Execute | | | |
| 6. Monitor | | | |
| 7. Modify | | | |
| 8. Conclude | | | |

## Competing Solutions
| Competitor | How It Does the Job | Where It Falls Short |
|------------|---------------------|---------------------|

## Desired Outcomes
**Minimize:**
- [Negative outcome to reduce]

**Maximize:**
- [Positive outcome to increase]

## Unmet Needs Found
[Ranked by severity]

## Job Story Assessment
| Story | Job Step | Outcome-Focused? | Verdict |
|-------|----------|-------------------|---------|

## Requirements Gap Analysis
- **Requirements without a job:** [scope creep]
- **Jobs without a requirement:** [gaps]

## Metrics Assessment
[Are they measuring job completion or feature usage?]

## Recommendations
[Specific rewrites and additions]
```

4. Offer to rewrite the PRD's job stories and requirements based on the analysis.

---

## Key Questions to Surface

Throughout the analysis, ask these Christensen-inspired questions:
- "What job is the user hiring this product to do?"
- "What progress are they trying to make?"
- "What are they switching from? (Including 'nothing')"
- "What are they giving up by using this?"
- "What does success look like for this job?"
- "What surprising competitors exist for this job?"

## Christensen's Wisdom

"The jobs that arise in people's lives are the fundamental causal driver behind everything."

Products don't fail because of features. They fail because they don't help people make progress on jobs they care about. Understand the job, and the features become obvious.
