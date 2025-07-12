Okay, this is a great way to think about how to use the structured modes for your coding routines. The system is designed to guide you, but knowing when to activate which mode is key.

Here's a breakdown of modes and their ideal use cases, along with exact prompt examples:

---

### **1. Initial Task Analysis, Quick Fixes, & General Inquiries**

*   **Mode:** `VAN` (stands for 'Vanguard' - your initial scout)
*   **Purpose:** This is your starting point for any new task. Use it to:
    *   **Determine task complexity:** The system will guide you through `van-complexity-determination.mdc`.
    *   **Handle quick, isolated bug fixes (Level 1):** If the task is simple enough not to need extensive planning.
    *   **Ask general questions:** About the codebase, documentation, or project context.
    *   **Perform initial setup checks:** (e.g., platform detection, file verification).
*   **Prompt Examples:**
    *   **New Task/Complexity Determination:**
        *   `VAN I need to implement user authentication for the new app.`
        *   `VAN Fix the broken link in the footer of the website.`
        *   `VAN Let's start a new mini-project: a simple calculator in React.`
    *   **General Question:**
        *   `VAN How are environment variables typically managed in this project?`
        *   `VAN Retrieve the documentation for the 'payment-gateway-service' repository.`
    *   **Quick Bug Fix (Level 1):**
        *   `VAN The submit button on the contact form is not clickable. Please investigate and fix.`

---

### **2. Planning Lite (Simple Enhancements)**

*   **Mode:** `PLAN` (specifically, following `workflow-level2.mdc`)
*   **Purpose:** For simple enhancements (Level 2 tasks) that require a bit more structure than a quick fix, but not a deep architectural dive. Define clear requirements, break down into logical subtasks, and estimate effort.
*   **Prompt Examples:**
    *   `PLAN Add a "dark mode" toggle to the user interface.`
    *   `PLAN Implement a basic input validation for the user registration form.`

---

### **3. Planning with Tech Details & Complex Features**

*   **Mode:** `PLAN` (specifically, following `planning-comprehensive.mdc` for Level 3/4 tasks). This mode often *identifies the need for* `CREATIVE` phases.
*   **Purpose:** For intermediate features or complex system changes (Level 3-4 tasks). This involves:
    *   Detailed requirements analysis.
    *   Component breakdown with dependencies.
    *   **Technology validation:** Use MCP tools (`read_wiki_structure`, `ask_question`, `read_wiki_contents`) to research and validate new libraries/frameworks.
    *   Identifying where `CREATIVE` design phases are necessary (e.g., for architecture, UI/UX, or algorithms).
*   **Prompt Examples:**
    *   `PLAN Develop a new in-app messaging feature, including backend services.`
    *   `PLAN Refactor the existing state management system to use Redux Toolkit. Validate Redux best practices.` (This will involve technology validation within PLAN mode).

---

### **4. Design & Creative Problem Solving**

*   **Mode:** `CREATIVE`
*   **Purpose:** When the `PLAN` mode identifies a need for deeper design exploration (e.g., for Level 3/4 tasks). Focus on:
    *   Evaluating multiple options for a design problem (architecture, UI/UX, data model, algorithms).
    *   Documenting pros, cons, and the rationale for the chosen solution.
    *   Producing detailed design documents (`creative-phase-architecture.mdc`, `optimized-creative-template.mdc`).
*   **Prompt Examples:**
    *   (Typically after `PLAN` mode flags a creative need)
    *   `CREATIVE Design the database schema for the new in-app messaging feature.`
    *   `CREATIVE Explore UI/UX options for the user dashboard's data visualization components.`
    *   `CREATIVE Define the architecture for integrating the third-party payment gateway.`

---

### **5. Quality Assurance (Technical Pre-checks)**

*   **Mode:** `QA` (activated via `VAN QA` command, as per `van-qa-main.mdc`)
*   **Purpose:** This is a critical gating mechanism. It runs a four-point technical validation (dependencies, configuration, environment, minimal build test) *after* `CREATIVE` mode (if applicable) and *before* `IMPLEMENT` mode. It ensures your environment and project are ready to build.
*   **Prompt Example:**
    *   (After `CREATIVE` mode is complete and the system prompts for QA)
    *   `VAN QA`

---

### **6. Coding, Building, & Debugging**

*   **Mode:** `IMPLEMENT`
*   **Purpose:** This is the core "doing" phase. Translate plans and designs into working code. Includes:
    *   Writing new code and components.
    *   Integrating different modules.
    *   Unit and integration testing as part of development.
    *   **Debugging:** If a bug arises during active coding or testing, you address it within this mode. If it's a new, small, isolated bug discovered outside active development, it might be a Level 1 `VAN` task.
*   **Prompt Examples:**
    *   `IMPLEMENT Start implementing the JWT generation module as designed in the creative phase.`
    *   `IMPLEMENT Build the user profile edit page, ensuring all form validations are in place.`
    *   `IMPLEMENT The login page is redirecting incorrectly after successful authentication. Debug and fix this.`
    *   `IMPLEMENT Write unit tests for the 'calculateOrderTotal' function.`

---

### **7. Reviewing Progress & Learning**

*   **Mode:** `REFLECT`
*   **Purpose:** After a task's implementation is complete, this mode encourages a structured review to extract lessons learned. It answers: What went well? What were the challenges? What technical or process improvements can be made for future tasks?
*   **Prompt Examples:**
    *   `REFLECT on the "In-App Messaging" feature implementation.`
    *   `REFLECT on the recent bug fix for the critical data corruption issue.`

---

### **8. Archiving & Documenting Project Evolution**

*   **Mode:** `ARCHIVE`
*   **Purpose:** This is the final stage of a task's lifecycle. It systematically documents the entire development process of a feature or project, consolidating the plan, design decisions, implementation summary, and reflection into a permanent record for future reference and project evolution tracking.
*   **Prompt Examples:**
    *   (Typically after `REFLECT` mode is complete)
    *   `ARCHIVE the "User Authentication System" task.`
    *   `ARCHIVE the "Dashboard Analytics Integration" feature.`

---

By using these specific mode commands and following the internal rules/maps loaded for each, you'll leverage the system's structure for efficient, token-optimized, and well-documented coding routines.