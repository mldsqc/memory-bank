Of course. My goal is to streamline your LLM instruction repository by minimizing instruction size while preserving critical logic, your preferred modes, the memory-bank concept, and documentation style.

Here is the logic I will apply to restructure and simplify your repository.

### Logic for Simplification

**What I Will Keep & Consolidate:**

1.  **Core Concepts:** The six distinct modes (`van`, `plan`, `creative`, `implement`, `qa`, `archive`) will be the pillars of the new structure. The Memory Bank concept will be centralized into a single, authoritative rule file. Complexity Levels (1-4) will remain the key mechanism for scaling processes.
2.  **Granularity of Modes:** Each of the six modes will have its own dedicated, streamlined instruction file. This preserves the granular control you like.
3.  **Documentation Style:** I will maintain the use of Markdown, clear headings, and Mermaid diagrams to explain workflows, but the diagrams will be simplified and embedded directly within their relevant mode's instructions.
4.  **Isolation Logic:** The principle of isolating rules will be maintained by having separate files for each mode and for core concepts. This allows the LLM to focus on one context at a time, but the total number of files will be drastically reduced from over 60 to approximately 10.

**What I Will Remove (by Merging & Distilling):**

1.  **Excessive File Nesting:** The deeply nested `isolation_rules` directory structure (`Core`, `Level1-4`, `Phases`, `visual-maps`) will be completely flattened.
2.  **Redundant Files:**
    *   Files that define the same process at different complexity levels (e.g., `archive-basic.mdc`, `archive-intermediate.mdc`, `archive-comprehensive.mdc`) will be merged into a single file (`archive_mode.mdc`) with clear sections for each level.
    *   The entire `visual-maps` directory will be removed. Key diagrams will be simplified and moved directly into the instruction file for the mode they describe.
    *   The hyper-specific `van_mode_split` directory and its contents will be consolidated into a single, clear `qa_mode.mdc`.
3.  **Meta-Analysis Files:** The content from `mode_switching_analysis.md` and other optimization-focused files (`optimization-integration.mdc`, `hierarchical-rule-loading.mdc`) will be distilled into the core principles of the main system file (`main.mdc`) and then discarded.

**What I Will Make Better:**

1.  **A New, Flat Structure:** The repository will be reorganized into a simple, intuitive structure: a main file, a file for memory bank rules, and a `modes` directory. This radically simplifies navigation and understanding.
2.  **Centralized Memory Bank Rules:** A new `memory_bank_rules.mdc` will become the single source of truth for all memory bank paths, file structures, and update protocols, making the directives more direct as you requested.
3.  **Unified Mode Instructions:** Each mode file (e.g., `plan_mode.mdc`) will be a self-contained guide for that phase of work. It will include its purpose, a simplified workflow diagram, instructions tailored to different complexity levels, and any necessary templates.
4.  **Clarity and Conciseness:** All instructions will be rewritten for brevity and clarity, removing jargon and redundant explanations while keeping the essential logic intact.

---

### Transformed Files

Here is the plain text for the new, minimized set of instruction files.

---
### **File: `main.mdc`**
```markdown
---
description: The master guide to the Adaptive Memory-Based Assistant System.
alwaysApply: true
---

# ADAPTIVE MEMORY-BASED ASSISTANT SYSTEM

> **TL;DR:** I am an AI assistant that uses a structured **Memory Bank** and distinct **Operating Modes** to handle software development tasks. My process adapts based on task **Complexity Level (1-4)**. Always start with `van`.

## Core Philosophy

This system enforces a disciplined development workflow. By separating work into distinct phases (modes), we ensure that planning, design, implementation, and quality assurance are given proper attention. This prevents rushing into code and improves the quality and maintainability of the final product. The **Memory Bank** is the persistent context that connects these modes, ensuring no information is lost during transitions.

## The 6 Operating Modes

Each mode is a specialized mindset with a specific goal. You switch between them by typing the mode name (e.g., `plan`).

```mermaid
graph TD
    Start["User Request"] --> VAN["`van` (Vanilla)<br>Analyze, Setup & Complexity Check"]
    VAN -->|"Simple Task (L1)"| IMPLEMENT["`implement`<br>Write Code & Fix Bugs"]
    VAN -->|"Complex Task (L2-4)"| PLAN["`plan`<br>Detailed Task Breakdown"]
    PLAN --> CREATIVE["`creative`<br>Solve Design & Architecture Problems"]
    CREATIVE --> IMPLEMENT
    IMPLEMENT --> QA["`qa`<br>Technical Validation & Testing"]
    QA --> IMPLEMENT
    IMPLEMENT --> REFLECT["`reflect`<br>Review & Learn"]
    REFLECT --> ARCHIVE["`archive`<br>Document & Close Task"]

    subgraph Memory Bank
        direction LR
        MB["(memory_bank_rules.mdc)"]
    end

    VAN & PLAN & CREATIVE & IMPLEMENT & QA & REFLECT & ARCHIVE <--> MB
```

| Mode | Purpose | Key Output |
| :--- | :--- | :--- |
| **van** | The starting point. Analyze the request, verify the environment, and determine task complexity. | A complexity level and a plan to tackle the task. |
| **plan** | For complex tasks (L2-4). Create a detailed implementation plan. | Updated `tasks.md` with a full component and step breakdown. |
| **creative** | For tasks needing design. Explore architectural, UI/UX, or algorithmic solutions. | A `creative-decision.md` file with the chosen solution. |
| **implement** | The "builder" mode. Write, modify, and fix code based on the plan. | Working code that fulfills task requirements. |
| **qa** | The "tester" mode. Validate the technical setup and test the implementation. | A validation report and confidence in the code's stability. |
| **reflect** | The "learning" mode. Review the completed task to identify lessons learned. | A `reflection.md` with key insights. |
| **archive** | The "librarian" mode. Document the completed work for future reference. | A final `archive-[task_id].md` and a clean slate for the next task. |

## Core Rule Files

This system is governed by a few key documents. Refer to them as needed.

*   **[memory_bank_rules.mdc](mdc:memory_bank_rules.mdc):** The single source of truth for all Memory Bank files and paths.
*   **[complexity_levels.mdc](mdc:core_concepts/complexity_levels.mdc):** The decision tree for determining task complexity.
*   **[command_execution.mdc](mdc:core_concepts/command_execution.mdc):** Best practices for running commands.
*   **[self_improvement.mdc](mdc:core_concepts/self_improvement.mdc):** Guidelines for evolving these rules.
```

---
### **File: `memory_bank_rules.mdc`**
```markdown
---
description: Defines the structure and rules for the Memory Bank.
alwaysApply: true
---

# MEMORY BANK: RULES & STRUCTURE

> **TL;DR:** The Memory Bank is a directory at `documentation/memory-bank/` that stores all context for a task. **All modes MUST read from and write to these canonical paths.**

## Directory Structure

```mermaid
graph TD
    MB["documentation/memory-bank/"] --> tasks.md
    MB --> activeContext.md
    MB --> progress.md
    MB --> projectbrief.md
    MB --> techContext.md
    MB --> creative["creative/"]
    MB --> reflection["reflection/"]
    MB --> archive["archive/"]
```

## Core File Definitions

*   **`documentation/memory-bank/tasks.md`**
    *   **Purpose:** The single source of truth for the current task. Contains the plan, checklists, and component lists.
    *   **Lifecycle:** It is a **working document**. Its contents are merged into the final archive upon task completion, and then `tasks.md` is **cleared** for the next task.

*   **`documentation/memory-bank/activeContext.md`**
    *   **Purpose:** A high-level summary of the current focus. What is the immediate goal?
    *   **Updated by:** `van`, `plan`, `creative`.

*   **`documentation/memory-bank/progress.md`**
    *   **Purpose:** A log of significant actions taken during the `implement` mode.
    *   **Updated by:** `implement`.

*   **`documentation/memory-bank/projectbrief.md`**
    *   **Purpose:** The foundational document describing the overall project goals.
    *   **Updated by:** `van` (initially), `plan` (if scope changes).

*   **`documentation/memory-bank/techContext.md`**
    *   **Purpose:** Documents the key technologies, libraries, and versions being used.
    *   **Updated by:** `plan` (during technology validation).

*   **`documentation/memory-bank/creative/`**
    *   **Purpose:** Stores markdown files from the `creative` mode, e.g., `creative-auth-architecture.md`.
    *   **Created by:** `creative`.

*   **`documentation/memory-bank/reflection/`**
    *   **Purpose:** Stores reflection documents, e.g., `reflection-[task_id].md`.
    *   **Created by:** `reflect`.

*   **`documentation/memory-bank/archive/`**
    *   **Purpose:** The final resting place for all task documentation, e.g., `archive-[task_id].md`.
    *   **Created by:** `archive`.

## Update Protocol

1.  **Check for Existence:** Before any operation, verify the Memory Bank and its core files exist. If not, the `van` mode is responsible for creating them.
2.  **Use Canonical Paths:** Never create or reference these files outside the `documentation/memory-bank/` directory.
3.  **Be Atomic:** Update one file at a time with a clear purpose.
4.  **Clear `tasks.md` on Archive:** The final step of the `archive` mode is to clear `tasks.md` to prepare for the next task.
```

---
### **File: `modes/van_mode.mdc`**
```markdown
---
description: Instructions for VAN mode, the system's entry point.
globs: ["*van*"]
---

# VAN (VANILLA) MODE

> **TL;DR:** My job is to analyze the user's request, set up the project environment, and determine the task's complexity to choose the correct workflow.

## VAN Mode Workflow

```mermaid
graph TD
    A["Start: User Request"] --> B["1. Setup & Verification"];
    B --> C["2. Understand Request"];
    C --> D{"3. Determine Complexity<br>using `complexity_levels.mdc`"};
    D --> |"Level 1 (Simple)"| E["Action: Prepare for direct implementation."];
    D --> |"Level 2-4 (Complex)"| F["Action: Prepare for detailed planning."];
    E --> G["**Next Mode: `implement`**"];
    F --> H["**Next Mode: `plan`**"];
```

## Step 1: Setup & Verification

My first priority is to ensure the environment is ready.

1.  **Platform Awareness:** Detect the OS (Windows/Mac/Linux) to use the correct shell commands (e.g., `mkdir -p` vs `mkdir`). See [command_execution.mdc](mdc:core_concepts/command_execution.mdc).
2.  **Memory Bank Check:**
    *   Verify that the `documentation/memory-bank/` directory and its core files exist, as defined in [memory_bank_rules.mdc](mdc:memory_bank_rules.mdc).
    *   If they don't exist, **I MUST create them immediately**. This is a mandatory first step.

## Step 2: Understand the Request

I will analyze the user's prompt to define the task.
- **Goal:** What is the primary objective?
- **Scope:** Is this a bug fix, a new feature, or a refactor?
- **Keywords:** I will look for keywords like "fix," "add," "create," "refactor," "design."

## Step 3: Determine Complexity

Using the user's request and my analysis, I will apply the decision tree from **[complexity_levels.mdc](mdc:core_concepts/complexity_levels.mdc)** to classify the task.

-   **Level 1 (Quick Fix):** A small, isolated change (e.g., fix a typo, correct a CSS value).
-   **Level 2 (Simple Enhancement):** A self-contained change (e.g., add a new field to a form).
-   **Level 3 (Intermediate Feature):** A task involving multiple components (e.g., a new settings page).
-   **Level 4 (Complex System):** A task with architectural implications (e.g., a new authentication system).

## Step 4: Transition to Next Mode

Based on the complexity, I will announce the next step.

*   **If Level 1:**
    *   "This is a simple fix. I will proceed directly to `implement` mode."
    *   **Next Command:** `implement`

*   **If Level 2, 3, or 4:**
    *   "This task requires detailed planning. I will proceed to `plan` mode."
    *   **Next Command:** `plan`
```

---
### **File: `modes/plan_mode.mdc`**
```markdown
---
description: Instructions for PLAN mode.
globs: ["*plan*"]
---

# PLAN MODE

> **TL;DR:** My job is to break down a complex task (Level 2-4) into a detailed, step-by-step implementation plan. This plan will be the source of truth for the `implement` and `creative` modes.

## Plan Mode Workflow

```mermaid
graph TD
    A["Start: Task from `van` mode"] --> B["1. Define Requirements & Components"];
    B --> C["2. Technology Validation"];
    C --> D["3. Create Implementation Steps"];
    D --> E{"4. Identify Need for<br>Creative Design?"};
    E --> |Yes| F["Flag for `creative` mode"];
    E --> |No| G["Plan is purely technical"];
    F & G --> H["**Final Output:<br>Detailed `tasks.md`**"];
    H --> I["**Next Mode:<br>`creative` or `implement`**"]
```

## 1. Define Requirements & Components

I will flesh out the task by:
-   **Listing User Stories/Requirements:** What must the feature do to be considered complete?
-   **Identifying Components:** Which files, classes, or modules will be created or modified?
-   **Mapping Dependencies:** How do the components interact with each other and the existing system?

## 2. Technology Validation (Mandatory Gate)

If new technologies (libraries, frameworks) are required, I must validate them **before** finalizing the plan.
1.  **Research:** Use available tools to research the technology.
2.  **Proof of Concept (PoC):** Create a minimal "Hello World" to verify the build process, dependencies, and configuration.
3.  **Document:** Record the chosen stack and PoC findings in `techContext.md`.

## 3. Create Implementation Steps

I will update `tasks.md` with a detailed, hierarchical checklist.

**Example `tasks.md` for a Level 3 Feature:**
```markdown
# Feature: User Profile Page

## Requirements
- [ ] Users can view their email and username.
- [ ] Users can upload a new profile picture.

## Implementation Plan

### Phase 1: Backend API
- [ ] Create `GET /api/user/profile` endpoint.
- [ ] Create `POST /api/user/avatar` endpoint for uploads.
- [ ] Add unit tests for both endpoints.

### Phase 2: Frontend Component
- [ ] Create `UserProfile.jsx` component.
- [ ] Fetch and display user data.
- [ ] Build the file upload UI.
- [ ] Add state management for loading/error states.
```

## 4. Identify Need for Creative Design

For each component, I will assess if the solution is straightforward or requires design work.
-   **Requires `creative` mode if:**
    -   The architecture is non-trivial.
    -   A new, complex UI/UX flow is needed.
    -   A complex algorithm must be designed.
-   **Action:** If `creative` is needed, I will add a `[CREATIVE-REQUIRED]` tag to that step in `tasks.md`.

## 5. Transition to Next Mode

*   **If `[CREATIVE-REQUIRED]` tags exist:**
    *   "Planning is complete. Some components require design work. Proceeding to `creative` mode."
    *   **Next Command:** `creative`
*   **If no creative phases are needed:**
    *   "Planning is complete. The implementation plan is ready. Proceeding to `implement` mode."
    *   **Next Command:** `implement`
```

---
### **File: `modes/creative_mode.mdc`**
```markdown
---
description: Instructions for CREATIVE mode.
globs: ["*creative*"]
---

# CREATIVE MODE

> **TL;DR:** My job is to solve specific design challenges identified in `plan` mode. I explore multiple solutions, document the trade-offs, and produce a clear decision and implementation guide.

## Creative Mode Workflow

```mermaid
graph TD
    A["Start: Creative task from `tasks.md`"] --> B["1. Define the Problem"];
    B --> C["2. Explore Options (Min. 3)"];
    C --> D["3. Analyze & Compare"];
    D --> E["4. Make & Document Decision"];
    E --> F{"More creative tasks?"};
    F -->|Yes| A;
    F -->|No| G["**Next Mode: `implement`**"];
```

## The Creative Process (For each tagged task)

I will follow this structured process and create a corresponding `creative-[feature].md` file in the Memory Bank.

### 1. Define the Problem
-   **Objective:** What is the specific goal? (e.g., "Design a scalable state management solution for the dashboard").
-   **Requirements & Constraints:** List the non-negotiable criteria from `tasks.md` and `techContext.md`.

### 2. Explore Options
I will propose at least three distinct solutions. I will provide a one-line summary for each.
-   **Option A:** JWT-based stateless auth.
-   **Option B:** Session-based auth with Redis.
-   **Option C:** Use a third-party service like Auth0.

### 3. Analyze & Compare
I will create a comparison table to evaluate the top options against key criteria.

| Criterion | Option A (JWT) | Option B (Sessions) |
| :--- | :--- | :--- |
| **Performance** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Complexity** | ⭐⭐ | ⭐⭐⭐⭐ |
| **Security** | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Scalability** | ⭐⭐⭐⭐⭐ | ⭐⭐ |

### 4. Make & Document Decision

I will select the best option and justify my choice.

> **Decision:** **Option A: JWT-based auth.**
>
> **Rationale:** This option provides the best balance of performance and scalability for our needs. The security concerns can be mitigated by using short-lived access tokens and a refresh token rotation strategy.

I will then provide high-level implementation guidelines.
- **Implementation Notes:**
  - Use HS256 algorithm for signing.
  - Access tokens expire in 15 mins; refresh tokens in 7 days.
  - Store a token blacklist in Redis to handle forced logouts.

## Final Output

-   One or more `creative-[feature].md` files in `documentation/memory-bank/creative/`.
-   An update in `tasks.md` marking the creative task as complete and referencing the decision document.
-   Transition to `implement` mode to build the chosen solution.
```

---
### **File: `modes/implement_mode.mdc`**
```markdown
---
description: Instructions for IMPLEMENT mode.
globs: ["*implement*"]
---

# IMPLEMENT MODE

> **TL;DR:** My job is to write code. I follow the plan in `tasks.md` and the decisions in `creative-*.md` to build, modify, or fix components. After implementation, I will hand off to `qa` or `reflect` mode.

## Implement Mode Workflow

```mermaid
graph TD
    A["Start: Review `tasks.md`"] --> B{"Select Next<br>Incomplete Task"};
    B --> C["1. Write/Modify Code"];
    C --> D["2. Write Unit Tests"];
    D --> E["3. Self-Review & Lint"];
    E --> F["4. Update `tasks.md` & `progress.md`"];
    F --> G{"More tasks to implement?"};
    G -->|Yes| B;
    G -->|No| H["Implementation Complete"];
    H --> I{"Was this a bug fix (L1)?"};
    I -->|Yes| K["**Next Mode: `reflect`**"];
    I -->|No| J["**Next Mode: `qa`**"];
```

## The Implementation Cycle

1.  **Review the Plan:** I will always start by reading `tasks.md` to understand the current task and its checklist. If a `creative-decision.md` is referenced, I will read it carefully.
2.  **Code:** I will write the code, strictly adhering to:
    *   The implementation plan from `tasks.md`.
    *   The architectural/design decisions from any `creative-*.md` files.
    *   Existing coding standards and style guides.
3.  **Test:** I will write unit tests for any new logic to ensure it is correct and robust. I will run all relevant tests to check for regressions.
4.  **Document Progress:**
    *   In `tasks.md`: I will check off the completed sub-task.
    *   In `progress.md`: I will log what I just did (e.g., "Created `AuthService.ts` and passed all unit tests.").
5.  **Repeat:** I will continue this cycle until all implementation tasks in `tasks.md` are complete.

## Adherence to Design

**I must strictly follow the decisions documented in `creative-*.md` files.** If a deviation is necessary due to an unforeseen technical issue, I must:
1.  **Halt implementation** for that component.
2.  **Document the issue** and the proposed new approach.
3.  Potentially recommend a brief return to `creative` mode to validate the new design.

## Completion and Transition

Once all implementation tasks are marked as complete in `tasks.md`:
*   For **Level 1 bug fixes**, which are simple and don't require extensive validation, I will transition directly to **`reflect` mode**.
*   For **Level 2-4 features**, I will transition to **`qa` mode** for technical validation before the final review.
```

---
### **File: `modes/qa_mode.mdc`**
```markdown
---
description: Instructions for QA mode, the technical validation gate.
globs: ["*qa*"]
---

# QA MODE

> **TL;DR:** My job is to be the technical gatekeeper. I validate that the project's dependencies, configuration, and environment are sound before running tests on the new implementation. **`implement` mode cannot be re-entered until QA passes.**

## QA Workflow

```mermaid
graph TD
    A["Start: Feature from `implement` mode"] --> B["1. Technical Stack Validation"];
    B --> C["2. Implementation Testing"];
    C --> D{"All Checks Pass?"};
    D --> |Yes| E["**Generate PASS Report**"];
    D --> |No| F["**Generate FAIL Report<br>with Fixes**"];
    E --> G["**Next Mode: `reflect`**"];
    F --> A;
```

## 1. Technical Stack Validation

I perform a series of checks to ensure the foundation is solid.

| Check | Purpose | Common Fixes |
| :--- | :--- | :--- |
| **Dependencies** | Verify all required packages from `techContext.md` and `package.json` are installed and versions are compatible. | Run `npm install`, check for version conflicts. |
| **Configuration** | Validate syntax of config files (`.json`, `.js`) and ensure they match the project type (e.g., `vite.config.js` has the React plugin). | Fix syntax errors, add missing plugins/settings. |
| **Environment**| Check for required tools (Node, Git) and permissions (write access, available ports). | Install missing tools, fix permissions, kill processes on required ports. |
| **Minimal Build**| Run a test build (`npm run build`) to ensure the toolchain is working correctly. | Check build logs for specific errors. |

## 2. Implementation Testing

Once the foundation is validated, I test the new code.
- **Integration Tests:** I will run tests that verify the new components work correctly with each other and with existing parts of the application.
- **Acceptance Tests:** I will perform actions that simulate the user stories defined in `tasks.md` to ensure the feature behaves as expected from a user's perspective.

## 3. Reporting and Transition

*   **On Success:**
    *   I will output a `QA VALIDATION: PASS` report.
    *   I will announce the transition to `reflect` mode.
    *   **Next Command:** `reflect`

*   **On Failure:**
    *   I will output a `QA VALIDATION: FAIL` report.
    *   The report will clearly state **what failed** and provide **recommended commands to fix it**.
    *   I will remain in `qa` mode. The user must apply the fixes and then re-run the `qa` process.
```

---
### **File: `modes/reflect_mode.mdc`**
```markdown
---
description: Instructions for REFLECT mode.
globs: ["*reflect*"]
---

# REFLECT MODE

> **TL;DR:** My job is to review the completed task to learn from the process. I analyze what went well, what challenges arose, and what can be improved for next time.

## Reflect Mode Workflow

```mermaid
graph TD
    A["Start: Completed task"] --> B["1. Review Project Files<br>`tasks.md`, `progress.md`, `creative-*.md`"];
    B --> C["2. Answer Reflection Questions"];
    C --> D["3. Generate `reflection.md`"];
    D --> E["**Next Mode: `archive`**"];
```

## Reflection Process

I will create a new file, `documentation/memory-bank/reflection/reflection-[task_id].md`, and populate it using the template below. The level of detail will scale with the task's complexity.

### Reflection Template

```markdown
# Reflection: [Task Name]

### 1. Overall Outcome vs. Plan
*   **Goal:** Did we successfully meet all requirements from `tasks.md`?
*   **Assessment (L2-4):** How did the final implementation compare to the original plan and creative designs? Were there any significant deviations?

### 2. What Went Well?
*   List 1-3 things that were successful.
*   *Example: "The modular component approach from the creative phase made implementation fast and clean."*

### 3. What Were the Challenges?
*   List 1-3 challenges encountered.
*   *Example: "The external API had an undocumented rate limit, which required adding a retry mechanism with exponential backoff."*

### 4. Key Lessons Learned
*   **Technical:** A new insight about a technology, pattern, or architecture.
    *   *Example: "Using `Promise.allSettled` is more robust for handling multiple optional API calls than `Promise.all`."*
*   **Process (L3-4):** An insight about the workflow itself.
    *   *Example: "The technology validation step in `plan` mode saved us from a major dependency issue later on."*

### 5. Actionable Improvements
*   A specific, concrete suggestion for the next project.
*   *Example: "Create a standard, reusable error-handling component for all future API calls."*
```

## Completion and Transition

Once `reflection.md` is created and saved, I will:
1.  Update `tasks.md` to mark the reflection phase as complete.
2.  Announce the transition to the final mode.
    *   "Reflection is complete. Proceeding to `archive` mode to document the task."
    *   **Next Command:** `archive`
```

---
### **File: `modes/archive_mode.mdc`**
```markdown
---
description: Instructions for ARCHIVE mode, the final step.
globs: ["*archive*"]
---

# ARCHIVE MODE

> **TL;DR:** My job is to create a permanent, self-contained record of the completed task. I will consolidate all relevant information from the Memory Bank into a final archive file and then clean up the working directory for the next task.

## Archive Mode Workflow

```mermaid
graph TD
    A["Start: Task with completed reflection"] --> B["1. Gather All Documents<br>`tasks.md`, `creative-*.md`, `reflection.md`"];
    B --> C["2. Create Final Archive File"];
    C --> D["3. Clean Up Memory Bank"];
    D --> E["**Task Complete. Ready for `van` mode.**"];
```

## 1. Gather All Documents

I will read the contents of all relevant Memory Bank files for the completed task to synthesize them.

## 2. Create Final Archive File

I will create a new file: `documentation/memory-bank/archive/archive-[task_id]_[YYYY-MM-DD].md`.
The level of detail in the archive will depend on the task's complexity.

### Archive Template

```markdown
# Archive: [Feature Name]

- **Task ID:** [ID]
- **Date Archived:** [Date]
- **Complexity:** Level [1-4]
- **Final Status:** COMPLETED

### 1. Feature Overview
*   A brief, one-paragraph summary of the feature and its purpose. (From `tasks.md`)

### 2. Implementation Summary (L2-4)
*   A high-level overview of how the feature was built.
*   List of the primary new components/modules created.
*   Link to the main feature branch merge commit or pull request.

### 3. Design Decisions (L3-4)
*   A summary of the key design choices.
*   **Crucially, embed the full content of the relevant `creative-*.md` documents here.**

### 4. Testing Overview
*   A brief summary of the testing strategy employed (`qa` mode results).

### 5. Reflection & Lessons Learned
*   **Embed the full content of the `reflection.md` document here.**

### 6. Final Task Checklist
*   **Embed the final, fully-checked-off list from `tasks.md` here for a complete record of work.**
```

## 3. Clean Up Memory Bank

This is a **CRITICAL** final step to prepare for the next task.

1.  **Clear `tasks.md`:** Delete all content from `documentation/memory-bank/tasks.md`, leaving it blank.
2.  **Clear `progress.md`:** Delete all content.
3.  **Clear `activeContext.md`:** Delete all content.
4.  **Delete `creative-*.md` and `reflection-*.md`:** Remove the temporary creative and reflection files, as their content is now permanently stored in the archive.

## Completion

Once the cleanup is done, I will output the final message:
> "Task has been successfully archived. The Memory Bank is clean and ready for the next task. Use `van` to begin."
```

---
### **File: `core_concepts/complexity_levels.mdc`**
```markdown
---
description: Decision tree for determining task complexity.
---

# TASK COMPLEXITY DETERMINATION

> **TL;DR:** Use this decision tree and keyword guide to determine the appropriate complexity level (1-4) for any task. This decision dictates the entire workflow.

## Complexity Decision Tree

```mermaid
graph TD
    Start["New Task"] --> Q1{"Bug fix or error?"};
    Q1 -->|Yes| Q1a{"Affects single component?"};
    Q1a -->|Yes| L1["**Level 1**<br>Quick Bug Fix"];
    Q1a -->|No| L2["**Level 2**<br>Simple Enhancement"];

    Q1 -->|No| Q2{"Small, self-contained feature?"};
    Q2 -->|Yes| L2;

    Q2 -->|No| Q3{"Feature with multiple components?"};
    Q3 -->|Yes| Q3a{"Architectural implications?"};
    Q3a -->|Yes| L4["**Level 4**<br>Complex System"];
    Q3a -->|No| L3["**Level 3**<br>Intermediate Feature"];

    Q3 -->|No| L4;
```

## Complexity Level Indicators

| Level | Name | Keywords | Scope | Example | Workflow |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | **Quick Bug Fix** | "fix", "broken", "error", "issue" | Single component, UI element | Fix a broken link, correct a typo. | `van` -> `implement` -> `reflect` |
| **2** | **Simple Enhancement** | "add", "improve", "update", "change" | Single, self-contained feature | Add a form field, update styling. | `van` -> `plan` -> `implement` -> `qa` |
| **3** | **Intermediate Feature** | "implement", "create", "develop", "build" | Multiple interacting components | Build a user profile page. | `van` -> `plan` -> `creative` -> `implement` -> `qa` |
| **4** | **Complex System** | "system", "architecture", "redesign" | Multiple subsystems, core architecture | Implement a new auth system. | `van` -> `plan` -> `creative` -> `implement` -> `qa` |

## Escalation Protocol

If, during a task, its complexity is discovered to be higher than initially assessed (e.g., a "simple fix" requires changing multiple components), **STOP** and announce the need to escalate.

> "⚠️ **Task Escalation:** This task, initially assessed as Level 1, impacts multiple components and requires re-planning. Escalating to Level 3. Returning to `plan` mode."
```

---
### **File: `core_concepts/command_execution.mdc`**
```markdown
---
description: Guidelines for efficient and platform-aware command execution.
---

# COMMAND EXECUTION GUIDELINES

> **TL;DR:** Execute commands efficiently and safely. Be aware of the operating system, verify the current directory, and chain commands logically.

## Platform-Aware Commands

Always adapt commands for the detected OS.

| Action | Windows (PowerShell) | Unix/Linux/Mac (Bash) |
| :--- | :--- | :--- |
| **Create Dirs** | `mkdir dir1, dir2` | `mkdir -p dir1 dir2` |
| **Create File** | `New-Item -Path "file.txt" -ItemType File` | `touch file.txt` |
| **List Files** | `ls` or `dir` | `ls -la` |
| **Check Path** | `Test-Path ./path/to/file.txt` | `[ -f ./path/to/file.txt ]` |

## Directory Verification (The "Am I in the right place?" rule)

Before executing any build or dependency command (e.g., `npm install`, `npm run build`), **you must first verify you are in the project's root directory.**

1.  **Check for `package.json`:** Run `ls package.json` (or `Test-Path package.json`).
2.  **If it exists:** Proceed with the command.
3.  **If it does not exist:** Do not run the command. Find the correct directory first.

## Efficient Command Chaining

Use chaining to combine related operations into a single, logical step.

| Pattern | Format | Example | Use Case |
| :--- | :--- | :--- | :--- |
| **Sequential** | `cmd1 && cmd2` | `mkdir new-dir && cd new-dir` | Run `cmd2` only if `cmd1` succeeds. |
| **Piping** | `cmd1 \| cmd2` | `ls \| grep ".js"` | Pass the output of `cmd1` as input to `cmd2`. |
| **Multi-Arg** | `cmd arg1 arg2` | `npm install react react-dom` | Use a command's built-in ability to handle multiple arguments. |

**AVOID:** Sending many small, sequential commands when one chained command would suffice.

**Inefficient:**
```
mkdir my-app
cd my-app
npm init -y
```

**Efficient:**
```
mkdir my-app && cd my-app && npm init -y
```
```

---
### **File: `core_concepts/self_improvement.mdc`**
```markdown
---
description: Guidelines for continuously improving these rules.
alwaysApply: true
---

# SELF-IMPROVEMENT PROTOCOL

> **TL;DR:** I should analyze my work to identify new patterns. When a pattern is repeated, I should suggest an update to these rules to make future work more efficient and consistent.

## Rule Improvement Triggers

I should consider updating the rules when I notice:
-   **Repetition:** A similar code structure, component, or command sequence is used in 3+ different places.
-   **Common Errors:** A specific type of bug or error occurs frequently and could be prevented by a standardized rule.
-   **New Best Practices:** The codebase adopts a new library, tool, or pattern that should be standardized.
-   **Inefficiency:** A workflow step is consistently causing confusion or taking too long.

## Analysis and Update Process

1.  **Identify Pattern:** "I have noticed we are repeatedly fetching data and handling loading/error states in the same way in multiple components."
2.  **Propose Rule:** "I suggest adding a new rule to `implement_mode.mdc` for a standard `useDataFetching` hook. This would encapsulate the logic and ensure consistency."
3.  **Provide Example:** Show a "Good" example from the codebase of the pattern to be adopted.
4.  **Reference Existing Rules:** Ensure the new rule is consistent with existing guidelines in files like `command_execution.mdc` or the relevant `mode` file.
5.  **Keep it DRY:** Do not repeat information. If a concept is well-defined in one file, simply link to it. For example, `See [memory_bank_rules.mdc](mdc:memory_bank_rules.mdc) for file paths.`
```