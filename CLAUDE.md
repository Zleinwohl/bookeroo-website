# Workflow Orchestration

## 1. Plan Mode Default
- Enter plan mode for ANY non-trivial task (3+ steps or architectural decisions).
- If something goes sideways, STOP and re-plan immediately instead of continuing blindly.
- Use plan mode for verification steps, not only implementation.
- Write clear and detailed specs before beginning work to reduce ambiguity.

## 2. Subagent Strategy
- Use subagents when helpful to keep the main context window clean.
- Offload research, exploration, and parallel analysis to subagents when possible.
- For complex problems, allocate additional compute through subagents.
- Assign only one task per subagent to ensure focused execution.

## 3. Self-Improvement Loop
- After any correction from the user, update `tasks/lessons.md` with the pattern.
- Create rules that prevent the same mistake from occurring again.
- Continuously iterate on these lessons until the error rate drops.
- Review relevant lessons at the start of each new session.

## 4. Verification Before Completion
- Never mark a task complete without verifying that it works.
- Compare the behavior between the original implementation and your changes when relevant.
- Ask yourself: "Would a senior staff engineer approve this change?"
- Run tests, check logs, and demonstrate correctness before declaring success.

## 5. Demand Elegance (Balanced)
- For non-trivial changes, pause and ask: "Is there a more elegant solution?"
- If a fix feels hacky, reconsider and implement the cleaner solution.
- Skip this process for simple or obvious fixes — avoid over-engineering.
- Critically review your own work before presenting it.

## 6. Autonomous Bug Fixing
- When given a bug report, diagnose and fix it proactively.
- Investigate logs, errors, and failing tests to determine the root cause.
- Resolve issues without requiring excessive user hand-holding.
- Fix failing CI tests when possible.

---

# Implementation Safety Rules

## 7. Preserve Existing Implementation
- Do NOT modify anything unless explicitly instructed.
- Treat all existing code, layout, and functionality as intentional.
- Avoid refactoring, renaming, restructuring, or improving unrelated areas.
- Implement the smallest possible change required to fulfill the request.
- Minimize the surface area of modifications.

## 8. Clarify Requirements Before Acting
- If any requirement, context, or specification is unclear, ask questions before implementing.
- Do NOT assume missing requirements.
- Ask precise follow-up questions about:
  - scope
  - expected behavior
  - UI/UX expectations
  - edge cases
- Prefer clarification over guessing.

## 9. No Silent Changes
- Never introduce changes beyond what was explicitly requested.
- If you notice potential improvements, bugs, or optimizations outside the request:
  - Do NOT implement them automatically.
  - Suggest them separately for approval.
- Maintain strict alignment with the requested scope.

---

# Task Management

1. **Plan First**
   Write the plan in `tasks/todo.md` with clear and checkable items.

2. **Verify Plan**
   Review and confirm the plan before beginning implementation.

3. **Track Progress**
   Mark tasks complete as progress is made.

4. **Explain Changes**
   Provide a high-level explanation of changes at each step.

5. **Document Results**
   Add a review section to `tasks/todo.md`.

6. **Capture Lessons**
   Update `tasks/lessons.md` whenever mistakes or corrections occur.

---

# Core Principles

- **Simplicity First**
  Make every change as simple as possible. Avoid unnecessary complexity.

- **No Laziness**
  Find root causes instead of implementing temporary fixes.

- **Minimal Impact**
  Changes should touch only what is necessary and avoid introducing new bugs.

- **Respect Existing Code**
  Assume the existing implementation is correct unless proven otherwise.

- **Clarity Over Assumption**
  When in doubt, ask questions rather than guessing.
