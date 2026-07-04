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

## 🚀 Quick Start: Setup & Usage Guide

To successfully configure, initialize, and run this agent-template for your development:

### 1. Open the Template Workspace
Ensure this template repository folder is open as the root workspace in your IDE (e.g. VS Code, Cursor) where your AI agent is active.

### 2. Configure Git Repository
Ensure Git is initialized in the workspace and connected to your target remote repository.

* **If git is already initialized pointing to agent-template (e.g. you cloned this project directly):**
  Change the remote URL to your new repository:
  ```bash
  git remote set-url origin <your-repository-url>
  ```

* **If you want to start with a fresh git commit history:**
  Delete the existing git database and re-initialize it:
  * **PowerShell (Windows):**
    ```powershell
    Remove-Item -Recurse -Force .git
    git init
    git remote add origin <your-repository-url>
    ```
  * **Bash (macOS/Linux):**
    ```bash
    rm -rf .git
    git init
    git remote add origin <your-repository-url>
    ```

* **If starting in a completely new/empty folder:**
  Initialize git and add your remote:
  ```bash
  git init
  git remote add origin <your-repository-url>
  ```

### 3. Initiate the Project Kickoff (`/kickoff`)
To start building your actual project within this skeleton, tell the agent to run the `/kickoff` skill. Paste the kickoff prompt into the AI chat:
> "I have a new project idea: `[INSERT YOUR PROJECT IDEA/CONCEPT]`. Run the `/kickoff` skill. Begin Phase 1 and interview me to define the tech stack, data isolation, and architecture."

This command launches the Project Director workflow:
* **The Spec & Tactical Interview:** The agent will grill you with questions to clarify database normalization, concurrency, and architecture rules, and automatically update `CONTEXT.md`.
* **Verification Metrics:** The agent will prompt you to set deterministic success criteria (concurrency thresholds, test coverage, etc.).
* **PRD & Backlog Generation:** Once the synthesized PRD is approved, the agent will convert it into actionable task list and populate issues using `/to-issues`.

### 4. Implement Tasks under strict TDD
Once the backlog issues are generated, pick up the first task (e.g., Issue #1 scaffold) and trigger the code execution loop:
> "Let's resolve Issue #1. Activate the `/tdd` skill to implement it under the strict Red-Green-Refactor loop."

---

## 🚀 Phase 0: Agent-Driven Initialization & Scaffolding

To quickly scaffold a new project or initialize an existing folder with this template (which pre-bundles all required skills, including `/kickoff`, `/tdd`, `/to-prd`, `/to-issues`, and `/grill-with-docs`) in a single step, run the following:

### Setup a New Project in the Current Directory
For a brand new project, execute this single terminal command:
```bash
npx -y giget@latest github:AryanMotiani/agent-template .
```

### Alternatively, Add the Template to an Existing Project Folder
Run this command to force-copy the skeleton and skills into your existing project:
```bash
npx -y giget@latest github:AryanMotiani/agent-template . --force
```

*(Note: Since all skills are pre-copied, they are instantly available without any secondary installation steps!)*


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
