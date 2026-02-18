# 📄 TASK_TEMPLATE.md
> **USER INSTRUCTIONS**: Use this template whenever you give the AI a new task. Copy-paste the "Minimal Usage" example at the bottom for quick tasks.

High-Signal Engineering Task Template
Use this template for all non-trivial tasks.

🔎 TASK
Short, clear action statement.
Example:Implement User Authentication with JWT

🎯 GOAL
What must exist when this task is complete?
Be measurable.
Example:
* Users can login/register
* JWT stored and restored
* Protected routes working

📦 SCOPE
What must be included?
* Features
* Pages
* State changes
* Services
* Tests
* Integration points
Keep bullet-based.

🔗 INTEGRATION
Where does this connect?
* Existing services?
* Store?
* Router?
* Middleware?
* Database?
This prevents architectural drift.

🚧 CONSTRAINTS
Hard rules for this task.
Examples:
* Use existing service layer
* Do not introduce new dependencies
* Follow state ownership map
* Minimal surface change
* No schema modification

🚫 NON-GOALS
What must NOT be done?
Examples:
* No refresh token
* No RBAC
* No performance optimization
* No UI redesign
This prevents scope creep.

🧠 ASSUMPTIONS (Optional)
If backend shape or environment is assumed, state it.
Example:
* Backend returns { data, message }
* Access token in response body

🧪 REQUIRED TESTS
Minimum validation:
* 1 happy path
* 1 failure case
* 1 error handling case
Optional:
* Regression case

📁 EXPECTED OUTPUT STRUCTURE
Define if needed:
* New files
* Modified files
* No full rewrites
* Diff-only changes

Why This Works
It forces:
* Clear scope
* Clear boundaries
* Clear integration awareness
* Clear expectations
* Clear non-goals
It avoids:
* Long storytelling prompts
* Repeated architecture explanation
* AI guessing scope

🔥 Example Minimal Usage
Instead of writing 40 lines:
You write:

TASK: Add sorting to ModelsPage

GOAL:
Allow sorting by price (asc/desc)

SCOPE:
- Update ModelsPage only
- No backend change
- Local state only

CONSTRAINTS:
- No global state
- No new dependency

NON-GOALS:
- No filters
- No pagination changes
That’s enough.
Your contract + project context handle the rest.
