Review a PRD for completeness and quality.

1. Read the PRD file specified by the user. If no file is specified, list the files in `prds/` and ask which one to review.
2. Read `docs/writing.md` for the review criteria.
3. Evaluate the PRD against every item in the checklist:
   - Is the problem clearly stated? Would a new team member understand it?
   - Are job stories specific enough that an engineer could build from them?
   - Are functional requirements testable?
   - Are success metrics measurable with specific numbers?
   - Is there an out-of-scope section?
   - Are risks acknowledged honestly?
   - Is the Status field set correctly?
   - Does the filename follow `YYYY-MM-DD_short-description.md`?
4. Score each item as PASS, NEEDS WORK, or MISSING.
5. Provide specific, actionable suggestions for anything that isn't PASS.
6. End with an overall verdict: Ready for Review, Needs Revision, or Major Gaps.
