# 📄 PROJECT_CONTEXT.md
> **USER INSTRUCTIONS**: Fill this file with your project's specific architectural truths. When you start a task, tell the AI: *"Reference `PROJECT_CONTEXT.md` for architectural alignment."*

Project Architecture & Operational Context
This document defines the architectural truth, constraints, assumptions, and structural boundaries of the project.
AI must use this file as the authoritative reference for architectural alignment.
This file contains high-signal information only.It is not a diary or change log.

1️⃣ Project Overview
Project Name: [Your Project Name]Project Type: (Mobile App / Web App / Backend API / Full Stack / SaaS / etc.)
Primary Purpose:Short 1–2 sentence description of what this system does.
Example:A community platform where employees can post updates, react, message, and receive real-time notifications.

2️⃣ Tech Stack
Frontend
* Framework:
* Language:
* State Management:
* Form Handling:
* Styling System:
* Navigation:
Backend
* Runtime:
* Framework:
* Authentication Strategy:
* Validation Library:
* Real-time Engine (if applicable):
Database
* Type:
* ORM / Query Builder:
* Migration Tool:
* Indexing Strategy:
Infrastructure
* Hosting:
* CI/CD:
* Monitoring:
* Logging:

3️⃣ Architectural Decisions (Locked)
These decisions must not be changed unless explicitly requested:
* All API calls go through a centralized service layer.
* No direct HTTP calls inside UI components.
* Feature-based folder structure.
* Centralized error normalization.
* JWT-based authentication.
* Minimal global state usage.
* No heavy dependencies without strong justification.
* Strict typing across layers.
These are non-negotiable defaults.

4️⃣ Folder Structure Convention
Frontend Example:

/src
  /features
  /components
  /services
  /store
  /utils
  /types
Backend Example:

/src
  /controllers
  /services
  /repositories
  /middlewares
  /routes
  /utils
AI must follow existing structure patterns.

5️⃣ State Ownership Map
This defines how state is distributed and who owns truth.
Global State (Allowed Only If Necessary)
Used only for:
* Auth user session
* Auth tokens (memory-level)
* Global theme
* Global notifications
* Real-time connection status
Global state must remain minimal.

Local State (Default Rule)
Use local state for:
* Form inputs
* Modal visibility
* Component-specific toggles
* Temporary filters
* View-only derived state
Default principle:
Local first. Promote to global only when required.

Must Never Become Global
* Raw API responses
* Temporary form data
* Derived UI flags
* Pagination cursors
* Isolated loading flags
* Transport-layer metadata
Global state is not a dumping ground.

Server-Authoritative Data
The server is the source of truth for:
* User profile
* Permissions
* Roles
* Financial data
* Counts
* Real-time events
Client may cache — server defines truth.

6️⃣ Service Layer Contract
All services must:
* Return typed DTOs only
* Never return raw Axios/HTTP responses
* Normalize error shape
* Never mutate input or output data
* Not contain UI logic
* Not directly update global state
Transport layer must not leak into business logic.

DTO Rule
Services return clean domain objects.
Not:
AxiosResponse<User>
But:
UserDTO

Error Normalization Rule
All services must normalize errors to:

{ message: string }
UI and business logic must never depend on transport-layer errors.

7️⃣ Validation Standards
* Email must follow standard format.
* Password minimum length defined.
* All forms show inline validation errors.
* Backend re-validates all inputs.
* Never trust client-only validation.

8️⃣ Error Handling Standards
* API returns structured errors.
* No stack traces exposed to client.
* No silent failures.
* All async flows handle loading + failure state.
* Defensive guards for null/undefined.

9️⃣ Security Assumptions
* JWT-based authentication.
* Access + refresh token flow.
* Passwords hashed securely.
* Sensitive env variables not exposed to client.
* Role-based access control enforced server-side.

🔟 Performance Constraints
* Avoid unnecessary re-renders.
* Avoid recreating arrays/objects in render.
* Memoize heavy components when justified.
* Optimize only when measurable issue exists.
* No premature micro-optimization.

11️⃣ Known Issues / Lessons Learned
Document past real issues here:
* Re-render issues caused by recreated arrays.
* Socket listener duplication caused memory leak.
* Token refresh race condition previously occurred.
* Duplicate API calls from improper effect dependencies.
This section prevents repeating mistakes.

12️⃣ API Assumptions
* Standard response shape:{ data, message }
* 
* Error shape:{ message }
* 
* Auth routes require Bearer token.
* Backend returns ISO date strings.

13️⃣ Non-Goals
This system is NOT optimizing for:
* Microservices architecture
* Enterprise multi-tenancy
* Event-driven architecture
* Offline-first architecture
* Massive-scale distributed systems
Avoid overengineering.

14️⃣ Scaling Assumptions
* Expected scale: (define approximate user range)
* Real-time concurrency expectation:
* Database growth expectation:
Design must match realistic scale.

15️⃣ Change Sensitivity Areas
These areas require extra caution:
* Authentication system
* Token refresh flow
* Database schema
* Payment or financial logic
* Real-time socket layer
AI must apply stability-first thinking here.

16️⃣ Coding Style Preferences
* Prefer explicit typing.
* Prefer named exports.
* Prefer early returns over nested conditions.
* No deep nested conditionals.
* Keep files focused and small.

17️⃣ Stability Principles
When in doubt:
* Preserve behavior.
* Avoid breaking changes.
* Avoid unnecessary structural changes.
* Minimize surface area of modification.
* Keep system predictable.
