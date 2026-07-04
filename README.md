# ⚙️ Agentic Skeleton: Operations & Command Guide

This repository contains all required AI skills, rules, and configuration. The following guide dictates how to bootstrap AI-assisted development using this template. 

> [!NOTE]
> This repository is intended to bootstrap AI-assisted development. After scaffolding, all development takes place in your project repository—not in the template repository.

---

## ⚖️ The Golden Laws (What You Must Enforce)

As the Orchestrator, you must constantly hold the AI accountable to these standards. If it violates them, halt execution. 

1. **The Pedagogical Mandate:** Your goal is mastery over deep backend systems and AI/ML architectures. If the agent outputs complex logic (e.g., tensor operations, advanced concurrency, or strict Pydantic validation), force it to explain the *why* before you accept the code.
2. **Anti-Vibe Coding:** Code is never written without a blueprint. The Red-Green-Refactor loop (`/tdd`) is absolute.
3. **Data Rigor:** Never accept flat database schemas. Enforce BCNF normalization and robust concurrency management (avoiding reader-writer starvation).
4. **Context Authority:** The agent is forbidden from silently changing its own rules. All updates to `CONTEXT.md` or `SKILL.md` must be transparent and verified by you.

---

## 🚀 Quick Start: Scaffolding & Setup Guide

This skeleton copies AI workflow and configuration files into your project directory. 

### What Gets Copied
The template scaffold includes:
* **AI Skills:** Pre-configured capabilities (located in `.agents/skills/`) for standard developer tasks.
* **CONTEXT.md:** Global rules, ubiquitous language, and system architecture definitions.
* **AGENTS.MD:** Workspace mapping and skill routing tables.
* **skills-lock.json:** Secure lockfile specifying installed capabilities.

> [!NOTE]
> The scaffold ONLY adds AI workflow and configuration files. Your project source code remains untouched except where filenames conflict and `--force` is used.

---

## 🛤️ Choose Your Workflow

### Workflow A — New Project
If starting a brand new project in an empty directory:

1. **Initialize Directory & Git:**
   ```bash
   mkdir MyProject
   cd MyProject
   git init
   ```
2. **Scaffold the Workspace:**
   ```bash
   npx -y giget@latest github:AryanMotiani/agent-template .
   ```

---

### Workflow B — Existing Repository
If injecting the template into your primary project repository:

1. **Navigate to project directory:**
   ```bash
   cd your-existing-project-folder
   ```
2. **Scaffold with Force Overwrite:**
   ```bash
   npx -y giget@latest github:AryanMotiani/agent-template . --force
   ```
   > [!WARNING]
   > Direct use of `--force` overwrites any files with the same name in the current directory. Commit or back up any important work before using it.

---

## 🔍 Verification & First Steps

### 1. Verify Scaffolded Files
Confirm that your target project directory now contains the following essential skeleton files:
```text
.agents/
CONTEXT.md
AGENTS.MD
README.md
skills-lock.json
```
*(Note: The skills are copied directly into the project and should be available to your AI agent. If they are not detected immediately, reload the workspace or restart the AI session.)*

### 2. Initiate the Project Kickoff (`/kickoff`)
Once the folder has been scaffolded, open it in your IDE (e.g. VS Code, Cursor), and start the `/kickoff` skill. Paste this prompt into the AI agent chat:
> "I have a new project idea: `[INSERT YOUR PROJECT IDEA/CONCEPT]`. Run the `/kickoff` skill. Begin Phase 1 and interview me to define the tech stack, data isolation, and architecture."

This command launches the Project Director workflow:
* **The Spec & Tactical Interview:** The agent will grill you with questions to clarify database normalization, concurrency, and architecture rules, and automatically update `CONTEXT.md`.
* **Verification Metrics:** The agent will prompt you to set deterministic success criteria (concurrency thresholds, test coverage, etc.).
* **PRD & Backlog Generation:** Once the synthesized PRD is approved, the agent will convert it into an actionable task list and populate issues using `/to-issues`.

### 3. Implement Tasks under strict TDD
Once the backlog issues are generated, pick up the first task (e.g., Issue #1 scaffold) and trigger the code execution loop:
> "Let's resolve Issue #1. Activate the `/tdd` skill to implement it under the strict Red-Green-Refactor loop."

