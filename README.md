# MaWorkflow: Gated AI Agent Workflow & Modular Engineering Standards

**MaWorkflow** is a professional framework designed for AI coding agents (such as OpenCode) to transition from generic code generation to **structured software engineering**. It enforces a strict multi-phase lifecycle, preventing premature coding and ensuring production-ready client applications.

---

## Repository Structure

```text
MaWorkflow/
├── workflow.md               # Universal 5-phase lifecycle & critical agent persona
├── Skill/
│   └── client-artisan-workflow.md  # Tech-stack specific standard (Laravel, Tailwind, Alpine.js)
├── LICENSE
└── README.md

```

---

## Core Philosophy

1. **No Premature Coding:** Agents are strictly forbidden from writing code until architecture, database schemas, and documentation are fully agreed upon.
2. **The Proactive Critic:** The AI agent acts as a technical architect, challenging weak requirements and proposing robust alternatives.
3. **Modular Tech Stacks:** The root workflow remains constant, while tech-stack rules (`Skill/`) can be swapped or added (Laravel, Node.js, Go, Python).
4. **Scope Creep Management:** Includes a built-in protocol to safely handle mid-project client requirement changes.

---

## How to Use

1. Clone or register this workflow folder into your AI agent's skills/rules directory.
2. Start a new project workspace and invoke the workflow:
> *"Let's start Phase 1: PRD creation for our new client project."*


3. Fill out the PRD form, select your target tech stack skill from the `Skill/` folder, and let the agent guide you sequentially through System Design, UI/UX, Task Breakdown, and Implementation.