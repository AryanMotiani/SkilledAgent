# ⚙️ Agentic Skeleton: Operations & Command Guide

This document is your personal flight manual. It dictates how to initialize projects, route workflows, and enforce rigorous engineering standards using the Agent Skills architecture. 

---

## ⚖️ The Golden Laws (What You Must Enforce)

As the Orchestrator, you must constantly hold the AI accountable to these standards. If it violates them, halt execution. 

1. **The Pedagogical Mandate:** Your goal is mastery over deep backend systems and AI/ML architectures. If the agent outputs complex logic (e.g., tensor operations, advanced concurrency, or strict Pydantic validation), force it to explain the *why* before you accept the code.
2. **Anti-Vibe Coding:** Code is never written without a blueprint. The Red-Green-Refactor loop (`/tdd`) is absolute.
3. **Data Rigor:** Never accept flat database schemas. Enforce BCNF normalization and robust concurrency management (avoiding reader-writer starvation).
4. **Context Authority:** The agent is forbidden from silently changing its own rules. All updates to `CONTEXT.md` or `SKILL.md` must be transparent and verified by you.

---

## 🚀 Quick Start: Scaffolding & Setup Guide

To initialize your development folder with this skeleton (which pre-bundles all required skills, including `/kickoff`, `/tdd`, `/to-prd`, `/to-issues`, and `/grill-with-docs`) in a single step:

### 1. Scaffold the Project
Choose the command depending on your starting directory:

* **Setup a New Project in the Current Directory:**
  ```bash
  npx -y giget@latest github:AryanMotiani/agent-template .
  ```

* **Inject Template into an Existing Folder:**
  ```bash
  npx -y giget@latest github:AryanMotiani/agent-template . --force
  ```

*(Note: Since all skills are pre-copied, they are instantly available in `.agents/skills` without any secondary installation steps!)*

### 2. Initiate the Project Kickoff (`/kickoff`)
Once the folder has been scaffolded, open it in your IDE (e.g. VS Code, Cursor), and start the `/kickoff` skill. Paste this prompt into the AI agent chat:
> "I have a new project idea: `[INSERT YOUR PROJECT IDEA/CONCEPT]`. Run the `/kickoff` skill. Begin Phase 1 and interview me to define the tech stack, data isolation, and architecture."

This command launches the Project Director workflow:
* **The Spec & Tactical Interview:** The agent will grill you with questions to clarify database normalization, concurrency, and architecture rules, and automatically update `CONTEXT.md`.
* **Verification Metrics:** The agent will prompt you to set deterministic success criteria (concurrency thresholds, test coverage, etc.).
* **PRD & Backlog Generation:** Once the synthesized PRD is approved, the agent will convert it into actionable task list and populate issues using `/to-issues`.

### 3. Implement Tasks under strict TDD
Once the backlog issues are generated, pick up the first task (e.g., Issue #1 scaffold) and trigger the code execution loop:
> "Let's resolve Issue #1. Activate the `/tdd` skill to implement it under the strict Red-Green-Refactor loop."



---

## 🛤️ Phase 1: The Kickoff Routing

Choose your path based on what you have prepared.

### Path A: Starting from Scratch (Just an Idea)
You have a basic concept but need the agent to help you design the architecture. 

> **Prompt:** "I have a new project idea: [INSERT BRIEF IDEA]. Execute the `/kickoff` skill. Begin Phase 1 and interview me to define the tech stack, data isolation, and architecture."

### Path B: You Already Have a PRD or Implementation Plan
You wrote the documentation beforehand and want the agent to ingest it, update its context, and skip the initial interview.

> **Prompt:** "I already have the core implementation plan for this project. 
> 
> [PASTE YOUR PRD/PLAN HERE]
> 
> Execute the `/kickoff` skill, but **modify Phase 1**: Skip the interview questions. Instead, immediately ingest this documentation, extract the Ubiquitous Language, and update `CONTEXT.md` with the technical standards outlined above. Once complete, ask me for the Verification Metrics (Phase 2)."

---

## 🎯 Phase 2: Verification & Backlog

Once the alignment is complete (either via interview or ingestion), the agent will ask for your deterministic verification criteria. 

**Example responses to give the agent:**
* "API endpoints must pass 100% of test cases under 100ms."
* "The data ingestion pipeline must be completely decoupled from the user-facing API."
* "The database must strictly follow BCNF."

After you lock the criteria, authorize the agent to move forward:
> **Prompt:** "Verification criteria locked. Execute Phase 3 to finalize the PRD and run `/to-issues` to populate the backlog. Issue #1 must be the project directory scaffolding."

---

## 🛠️ Phase 3: Execution

With your GitHub/Linear issues created, drop into the strict engineering loop. Pick up the first issue and paste:

> **Prompt:** "The backlog is ready. Activate the `/tdd` skill to implement Issue #1. Follow the strict Red-Green-Refactor loop. Ensure all actions align with the architectural rules now defined in `CONTEXT.md`."
