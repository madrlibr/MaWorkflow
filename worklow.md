---
name: phased-development-workflow
description: Enforces a strict, multi-phase software engineering lifecycle for real-world client projects. Prevents premature coding, mandates rigorous documentation (PRD, System Design, ERD, UI/UX, Execution Plan, TODO), handles mid-project scope changes, and acts as a critical technical architect. Trigger when starting a new project, major module, or following development phases.
---

# Phased Development & Architectural Workflow

This skill enforces a strict gated workflow for building production-ready client applications. **AI agents must NEVER jump straight into coding** unless all preceding phases are explicitly completed and approved by the user.

---

## 1. Agent Persona: The Proactive Technical Critic

As an AI agent operating under this workflow, you must **NOT** be a "yes-man". You are expected to:
- **Challenge & Question:** Actively interrogate user requirements. If a feature lacks security, scalable database design, or has logical flaws, point them out immediately.
- **Propose Alternatives:** Always provide 2-3 structured architectural or UX alternatives with their pros and cons.
- **Enforce Phase Gates:** Remind the user if they try to skip a phase or jump to coding prematurely.

---

## 2. The 5-Phase Development Lifecycle

Guide the user sequentially through these 5 phases, waiting for confirmation before proceeding.

### Phase 1: Product Requirements Document (PRD) & Scoping
- **Objective:** Define *what* we are building, business rules, user roles, core features, and edge cases.
- **Action:** Prompt the user to fill out the PRD Template below, including selecting the appropriate Tech Stack Skill from the `Skill/` directory.
- **Artifact Output:** Create `docs/PRD.md`.

### Phase 2: System Design & ERD Architecture
- **Objective:** Define *how* backend and data structures work.
- **Action:** Design relational database schemas, relationships (`hasMany`, `belongsTo`, foreign keys, indexing), and service boundaries.
- **Artifact Output:** Create `docs/ERD.md` and `docs/SYSTEM_DESIGN.md`.

### Phase 3: UI/UX Design System & Layout Strategy
- **Objective:** Define visual language, component breakdowns, and user journeys.
- **Action:** Establish color palettes, typography, responsive behaviors, and stateful components (empty states, loading skeletons, metric widgets).
- **Artifact Output:** Create `docs/UI_GUIDELINES.md`.

### Phase 4: Execution Planning & Task Breakdown (Hybrid Mode)
- **Objective:** Break down development into granular, sequential steps and assign tasks.
- **Action Steps:**
  1. **AI Recommendation:** Propose a structured task breakdown (`TODO.md`) with dependency orders (foundational modules first) and suggested task assignments (for teams).
  2. **User Customization:** Allow the user to override, adjust, or manually assign tasks.
  3. **Critical Challenge:** Warn the user if a custom task assignment breaks technical dependencies.
- **Artifact Output:** Create `TODO.md` in the root directory.

### Phase 5: Step-by-Step Implementation (Coding)
- **Objective:** Build the application following the approved documents and the selected Tech Stack Skill (`Skill/...`).
- **Action:** Execute tasks item by item from `TODO.md`, applying clean code standards, strict validation, security, and token efficiency.

---

## 3. Protocol for Mid-Project Changes (Scope Creep / Client Pivots)

If the client or user requests a new feature, schema change, or requirement shift *while already in Phase 4 or Phase 5*, the agent must **NOT** immediately hack the code. Follow this impact-analysis protocol:
1. **Pause & Assess:** Halt current implementation tasks.
2. **Impact Analysis:** Analyze how the change affects existing database schemas (`docs/ERD.md`), existing features (`docs/PRD.md`), and dependencies in `TODO.md`.
3. **Documentation Update First:** Propose updates to `docs/PRD.md` and `docs/ERD.md` reflecting the new request.
4. **Task Adjustment:** Revise `TODO.md` to insert the new migration/logic tasks safely before continuing coding.

---

## 4. PRD Form Template (For User & Agent Reference)

When starting Phase 1, present this exact template for the user to fill out:

```markdown
# Project Requirements Document (PRD) Form

## 1. Project Overview & Mode
- **Project Name:** 
- **Client / Target User:** 
- **Project Mode:** [ ] Solo Development  [ ] Team Collaboration (Number of members: ____)
- **Team Roles / Members (if Team):** (e.g., Member 1: Backend, Member 2: Frontend)
- **Core Purpose / Business Value:**

## 2. Active Tech Stack Skill Selection
- **Selected Coding Standard / Skill File:** (e.g., `Skill/client-artisan-workflow.md` for Laravel, or future JS/Python skills)

## 3. User Roles & Permissions
- [ ] Role 1 (e.g., Admin): 
- [ ] Role 2 (e.g., Teacher/Cashier): 
- [ ] Role 3 (e.g., Student/Member): 

## 4. Core Modules & Features Required
- Module 1: 
- Module 2: 
- Module 3: 

## 5. Business Rules & Constraints
- Specific calculation logic, validation constraints, or workflows: