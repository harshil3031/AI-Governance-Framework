# 🤖 AI_EXECUTION_CONTRACT.md
> **USER INSTRUCTIONS**: This is your Engineering Standard. It ensures AI writes production-grade code. You can customize the `Code Standards` section to match your linter/style guide.

Universal Engineering Execution Contract
This document defines mandatory AI behavior for all feature creation, modification, refactoring, optimization, migration, hotfix, recovery, and review tasks in this project.

🎯 Goals
* Reduce prompt length
* Increase consistency
* Prevent overengineering
* Enforce architectural discipline
* Improve productivity
* Maintain production-grade quality
* Protect system stability
When I provide:
TASK: <feature name>
AI must apply this entire contract automatically.

1️⃣ Core Philosophy
* Simplicity > Cleverness
* Stability > Clean Rewrite
* Backward Compatibility > Aesthetic Improvement
* Minimal Safe Change > Large Rewrite
* Long-term Maintainability > Short-term Speed
Rules:
* Do not overengineer.
* Do not invent features not requested.
* Follow existing project structure.
* Make safe minimal assumptions if unclear.
* Focus on clean, maintainable, scalable code.

2️⃣ Architectural Discipline
Before implementing anything:
1. Identify which layer the task belongs to:
    * UI / Presentation
    * State Management
    * API / Networking
    * Business Logic
    * Database
    * Infrastructure
2. Maintain strict separation of concerns.
3. Do not mix UI and business logic unnecessarily.
4. Avoid direct API calls inside UI if a service layer exists.
5. Follow existing project conventions strictly.

3️⃣ Implementation Requirements
A. Internal Clarification (Keep Short in Output)
* What problem does this solve?
* What is the expected outcome?
* What assumptions are being made?

B. Code Standards (Mandatory)
All implementations must include:
* Clean folder structure
* Strict typing (no any)
* Proper error handling
* Loading states for async logic
* Edge case handling
* No duplicated logic
* No magic numbers
* No nested ternary operators
* No console logs in production
* Small, single-responsibility functions
Inline comments must explain WHY, not WHAT.

4️⃣ Validation Rules
If user input is involved:
* Required field validation
* Format validation (email, password, etc.)
* Clear, user-friendly error messages
* No exposure of internal system errors
Validation must be robust but not excessive.

5️⃣ Security Rules
If authentication or sensitive data is involved:
* Never store plaintext passwords
* Never expose internal stack traces
* Never log sensitive information
* Use secure token handling
* Strict input validation
* Avoid insecure defaults
Security is mandatory.

6️⃣ Testing Requirements
Every task must include:
* 1 Happy path test
* 1 Validation failure test
* 1 Error handling test
If modifying existing behavior:
* Include regression test if relevant.
Briefly explain what each test verifies.
Testing cannot be skipped.

7️⃣ Performance Awareness
* Avoid unnecessary re-renders
* Avoid recreating objects in render loops
* Use memoization only when justified
* Avoid premature optimization
* Mention performance-sensitive decisions
Optimization must not significantly reduce readability.

8️⃣ Refactor Mode
If TASK indicates refactoring:
* Preserve external behavior
* Preserve API contracts unless explicitly instructed otherwise
* Improve clarity and structure
* Remove duplication
* Improve readability
* Improve testability
* Keep public interfaces stable
* Avoid introducing new architecture unnecessarily
Refactoring must reduce complexity — not increase it.

9️⃣ Modification Rule
If modifying existing code:
* Change only what is necessary
* Do not rewrite stable modules
* Preserve naming conventions
* Maintain backward compatibility
* Avoid unnecessary formatting changes
* Avoid unrelated structural changes
* Do not introduce breaking changes unless explicitly requested
Minimal surface area change is mandatory.

🔟 Diff Awareness Rule
When modifying existing code:
* Show only changed sections if context allows
* Avoid reprinting entire files unless necessary
* Keep changes minimal and focused
* Preserve original formatting where possible
* Clearly indicate additions, removals, or modifications
Full file rewrites should occur only if technically required.

11️⃣ Backward Compatibility Rule
Unless explicitly instructed:
* Do not change API contracts
* Do not rename exported functions
* Do not alter response shapes
* Do not modify database schema
* Do not remove existing behavior
System stability must be preserved.

12️⃣ Performance Optimization Mode
If TASK indicates performance improvement:
* Identify the bottleneck (assume reasonable scenario if not provided)
* Improve measurable inefficiencies only
* Preserve existing behavior
* Avoid unnecessary refactoring
* Provide before/after reasoning
* Explain trade-offs
Focus on meaningful improvements — not micro-optimizations.

13️⃣ Migration Mode
If TASK indicates migration:
* Define migration scope clearly
* Identify impacted modules
* Preserve external behavior where possible
* Provide step-by-step migration plan
* Provide rollback strategy
* Identify risks and breaking changes
* Suggest incremental migration if feasible
Migration must prioritize stability.

14️⃣ Review Mode
If TASK indicates review:
* Identify architectural weaknesses
* Identify security risks
* Identify performance issues
* Identify code smells
* Suggest minimal, safe improvements
* Avoid suggesting unnecessary rewrites
Focus on impact, not stylistic preference.

15️⃣ Assumption Policy
If details are missing:
* Make the safest minimal assumption
* Clearly state it
* Do not block execution unless absolutely critical
Avoid unnecessary clarification questions.

16️⃣ Overengineering Guard
AI must NOT:
* Add abstraction layers for small features
* Introduce complex patterns without justification
* Add global state if local state is sufficient
* Add enterprise-level logging unnecessarily
* Add new libraries unless clearly required
Keep solutions pragmatic.

17️⃣ Hotfix Mode
If TASK indicates hotfix or urgent production issue:
* Fix only the specific issue reported
* Do not refactor unrelated code
* Do not introduce new abstractions
* Keep patch surface area minimal
* Preserve existing behavior outside the bug
* Avoid stylistic cleanup
* Include regression test if possible
Mindset:Speed + Safety > Clean Architecture
After fix, briefly explain:
* Root cause
* Why fix is minimal and safe
* Long-term improvement (separate from hotfix)

18️⃣ Failure Recovery Mode
If TASK indicates broken system or instability:
* Identify probable failure point
* Prevent further damage
* Restore safe operational state
* Preserve data integrity
* Avoid adding complexity
* Do not silently swallow critical errors
Add defensive guards if needed.Fail gracefully rather than crash.Do not hide systemic issues.
Mindset:System Survival > Feature Completeness

19️⃣ Root Cause Awareness Rule
When fixing bugs or performance issues:
* Identify likely root cause
* Avoid surface-level patching
* Explain briefly why issue occurred
* Propose minimal fix aligned with root cause
Never patch symptoms without acknowledging cause.

20️⃣ Consistency Enforcement Rule
When generating new code:
* Match existing naming conventions
* Match file structure
* Match code style
* Match error handling patterns
* Match response structures
Consistency > Personal Preference.

21️⃣ Scope Guard Rule
AI must not:
* Expand scope beyond requested TASK
* Add speculative improvements
* Add unrelated “nice-to-have” features
* Introduce future-proofing layers without request
Solve exactly the requested task — nothing more.

22️⃣ Change Impact Awareness Rule
When modifying code, consider:
* What depends on this module?
* Could this break other features?
* Is this part of a public API?
If risk exists, mention it briefly.

23️⃣ Minimal Output Discipline
* Avoid unnecessary verbosity
* Avoid repeating contract rules
* Avoid long essays
* Keep reasoning concise and sharp
Engineering clarity > Explanation length.

24️⃣ Rule Priority Order
If rules conflict, prioritize in this order:
1. System Stability
2. Data Integrity
3. Backward Compatibility
4. Minimal Surface Area Change
5. Simplicity
6. Performance
7. Aesthetic Improvements
Higher priority rule always wins.

✅ End of Contract
This contract overrides default verbose or experimental AI behavior.
All implementations must follow these rules unless explicitly instructed otherwise.
