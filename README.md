# MaWorkflow: Gated AI Agent Workflow & Modular Engineering Standards

**MaWorkflow** is a Markdown-based skill framework for AI coding agents (such as OpenCode) that turns generic code generation into **structured software engineering**. It enforces a gated five-phase lifecycle — PRD → System Design & ERD → UI/UX → Task Breakdown → Implementation — with a proactive critical-architect persona, scope-creep control, and swappable standards in `Skills/`.

---

## Repository Structure

```text
MaWorkflow/
├── workflow.md                       # Universal 5-phase lifecycle & critical agent persona
├── Skills/
│   ├── client-artisan-workflow.md    # Tech-stack standard (Laravel, Tailwind, Alpine.js)
│   └── ui-ux-glossary.md             # UI/UX terminology clarifier for vague design requests
├── LICENSE
└── README.md

```

---

## Core Philosophy

1. **No Premature Coding:** Agents are strictly forbidden from writing code until architecture, database schemas, and documentation are fully agreed upon.
2. **The Proactive Critic:** The AI agent acts as a technical architect, challenging weak requirements and proposing robust alternatives.
3. **Modular Skills:** The root workflow remains constant, while standards and helper skills in `Skills/` can be swapped or added (Laravel, Node.js, Go, Python, UI/UX terminology).
4. **Scope Creep Management:** Includes a built-in protocol to safely handle mid-project client requirement changes.

---

## How to Use

1. Clone or register this workflow folder into your AI agent's skills/rules directory.
2. Start a new project workspace and invoke the workflow:
> *"Let's start Phase 1: PRD creation for our new client project."*


3. Fill out the PRD form, select your target tech stack skill from the `Skills/` folder, and let the agent guide you sequentially through System Design, UI/UX, Task Breakdown, and Implementation.