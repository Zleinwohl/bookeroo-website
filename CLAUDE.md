\# Workflow Orchestration



\## 1. Plan Mode Default

\- Enter plan mode for ANY non-trivial task (3+ steps or architectural decisions).

\- If something goes sideways, STOP and re-plan immediately instead of continuing blindly.

\- Use plan mode for verification steps, not only implementation.

\- Write clear and detailed specs before beginning work to reduce ambiguity.



\## 2. Subagent Strategy

\- Use subagents when helpful to keep the main context window clean.

\- Offload research, exploration, and parallel analysis to subagents when possible.

\- For complex problems, allocate additional compute through subagents.

\- Assign only one task per subagent to ensure focused execution.



\## 3. Self-Improvement Loop

\- After any correction from the user, update `tasks/lessons.md` with the pattern.

\- Create rules that prevent the same mistake from occurring again.

\- Continuously iterate on these lessons until the error rate drops.

\- Review relevant lessons at the start of each new session.



\## 4. Verification Before Completion

\- Never mark a task complete without verifying that it works.

\- Compare the behavior between the original implementation and your changes when relevant.

\- Ask yourself: “Would a senior staff engineer approve this change?”

\- Run tests, check logs, and demonstrate correctness before declaring success.



\## 5. Demand Elegance (Balanced)

\- For non-trivial changes, pause and ask: “Is there a more elegant solution?”

\- If a fix feels hacky, reconsider and implement the cleaner solution.

\- Skip this process for simple or obvious fixes — avoid over-engineering.

\- Critically review your own work before presenting it.



\## 6. Autonomous Bug Fixing

\- When given a bug report, diagnose and fix it proactively.

\- Investigate logs, errors, and failing tests to determine the root cause.

\- Resolve issues without requiring excessive user hand-holding.

\- Fix failing CI tests when possible.



---



\# Implementation Safety Rules



\## 7. Preserve Existing Implementation

\- Do NOT modify anything unless explicitly instructed.

\- Treat all existing code, layout, and functionality as intentional.

\- Avoid refactoring, renaming, restructuring, or improving unrelated areas.

\- Implement the smallest possible change required to fulfill the request.

\- Minimize the surface area of modifications.



\## 8. Clarify Requirements Before Acting

\- If any requirement, context, or specification is unclear, ask questions before implementing.

\- Do NOT assume missing requirements.

\- Ask precise follow-up questions about:

&nbsp; - scope

&nbsp; - expected behavior

&nbsp; - UI/UX expectations

&nbsp; - edge cases

\- Prefer clarification over guessing.



\## 9. No Silent Changes

\- Never introduce changes beyond what was explicitly requested.

\- If you notice potential improvements, bugs, or optimizations outside the request:

&nbsp; - Do NOT implement them automatically.

&nbsp; - Suggest them separately for approval.

\- Maintain strict alignment with the requested scope.



---



\# Task Management



1\. \*\*Plan First\*\*  

&nbsp;  Write the plan in `tasks/todo.md` with clear and checkable items.



2\. \*\*Verify Plan\*\*  

&nbsp;  Review and confirm the plan before beginning implementation.



3\. \*\*Track Progress\*\*  

&nbsp;  Mark tasks complete as progress is made.



4\. \*\*Explain Changes\*\*  

&nbsp;  Provide a high-level explanation of changes at each step.



5\. \*\*Document Results\*\*  

&nbsp;  Add a review section to `tasks/todo.md`.



6\. \*\*Capture Lessons\*\*  

&nbsp;  Update `tasks/lessons.md` whenever mistakes or corrections occur.



---



\# Core Principles



\- \*\*Simplicity First\*\*  

&nbsp; Make every change as simple as possible. Avoid unnecessary complexity.



\- \*\*No Laziness\*\*  

&nbsp; Find root causes instead of implementing temporary fixes.



\- \*\*Minimal Impact\*\*  

&nbsp; Changes should touch only what is necessary and avoid introducing new bugs.



\- \*\*Respect Existing Code\*\*  

&nbsp; Assume the existing implementation is correct unless proven otherwise.



\- \*\*Clarity Over Assumption\*\*

&nbsp; When in doubt, ask questions rather than guessing.

---

## Product Context Reference (Read-Only)

The folder `./Bookeroo-` contains the **Bookeroo operator SaaS product codebase**.

This repository exists **only as a reference** so Claude can understand:

- product features
- terminology
- workflows
- UI structure
- capabilities of the platform

### Canonical Product File

The most current implementation of the product is:

`./Bookeroo-/booking-saas_12.jsx`

This file should be treated as the **canonical reference for the current product functionality**.

Other JSX files in that folder may represent earlier or alternate versions unless explicitly stated otherwise.

### Safety Rule

Claude must **never modify, refactor, rename, or write files inside the `./Bookeroo-` folder**.

This folder is strictly **read-only context**.

### Current Project Goal

The current project being developed in this workspace is:

**The public-facing Bookeroo marketing website.**

The purpose of referencing the product code is only to:

- understand how Bookeroo works
- extract accurate feature descriptions
- ensure marketing language matches real functionality
- inform website structure and messaging

All implementation work should occur **outside of the `./Bookeroo-` folder.**

---

## Product Feature Verification Rule

Before generating marketing content, feature descriptions, page structures, or product claims related to Bookeroo, Claude must first analyze the canonical product reference file:

`./Bookeroo-/booking-saas_12.jsx`

The purpose of this step is to ensure that all descriptions of Bookeroo's capabilities are grounded in the actual product implementation.

Claude should use this analysis to understand:

- available features
- product workflows
- user roles
- UI modules
- terminology used in the application

Claude must **not invent or assume features that are not supported by the product code**.

If a requested feature, capability, or workflow cannot be verified in the canonical product file, Claude should ask for clarification before including it in marketing content.

### Scope of This Rule

This rule applies whenever Claude is asked to:

- write marketing copy
- define product features
- design marketing website pages
- describe how Bookeroo works
- create SEO or AEO content about the product

This ensures that all public-facing messaging accurately reflects the real product.

---
