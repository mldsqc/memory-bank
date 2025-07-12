Here are all the optimized files, keeping your preferences for granularity, Markdown/Mermaid, and minimizing token usage and file count.

I have:
*   **Removed** the identified redundant files.
*   **Consolidated** content where appropriate (e.g., the critical Memory Bank verification check is now primarily in `file-verification.mdc`).
*   **Stripped down verbose prose** and **removed LLM-internal pseudocode** (JavaScript classes, PowerShell/Bash functions that *implement* the LLM's own logic, not external commands). The LLM already *is* the logic; it just needs the instructions and templates.
*   **Maintained** all Mermaid diagrams, checklists, and key templates.
*   **Fixed** duplicate YAML headers.

---

### **Optimized Repository Contents:**

```
├── cursor_rules.mdc
├── custom_modes
    ├── creative_instructions.md
    ├── implement_instructions.md
    ├── plan_instructions.md
    ├── reflect_archive_instructions.md
    └── van_instructions.md
├── isolation_rules
    ├── Core
    │   ├── Tools
    │   │   └── ask-documentation-question.mdc
    │   ├── command-execution.mdc
    │   ├── complexity-decision-tree.mdc
    │   ├── creative-phase-enforcement.mdc
    │   ├── creative-phase-metrics.mdc
    │   ├── documentation-retrieval.mdc
    │   ├── file-verification.mdc
    │   ├── hierarchical-rule-loading.mdc
    │   ├── memory-bank-paths.mdc
    │   ├── mode-transition-optimization.mdc
    │   └── platform-awareness.mdc
    ├── Level1
    │   └── optimized-workflow-level1.mdc
    ├── Level2
    │   ├── archive-basic.mdc
    │   ├── reflection-basic.mdc
    │   ├── task-tracking-basic.mdc
    │   └── workflow-level2.mdc
    ├── Level3
    │   ├── archive-intermediate.mdc
    │   ├── implementation-intermediate.mdc
    │   ├── planning-comprehensive.mdc
    │   ├── reflection-intermediate.mdc
    │   └── task-tracking-intermediate.mdc
    ├── Phases
    │   └── CreativePhase
    │   │   ├── creative-phase-architecture.mdc
    │   │   └── optimized-creative-template.mdc
    ├── main-optimized.mdc
    └── visual-maps
    │   ├── archive-mode-map.mdc
    │   ├── creative-mode-map.mdc
    │   ├── implement-mode-map.mdc
    │   ├── plan-mode-map.mdc
    │   ├── qa-mode-map.mdc
    │   ├── reflect-mode-map.mdc
    │   ├── van-mode-map.mdc
    │   └── van_mode_split
    │       ├── van-complexity-determination.mdc
    │       ├── van-platform-detection.mdc
    │       ├── van-qa-checks
    │           ├── build-test.mdc
    │           ├── config-check.mdc
    │           ├── dependency-check.mdc
    │           └── environment-check.mdc
    │       ├── van-qa-main.mdc
    │       ├── van-qa-utils
    │           ├── common-fixes.mdc
    │           ├── mode-transitions.mdc
    │           ├── reports.mdc
    │           └── rule-calling-guide.mdc
└── self_improve.mdc
```

---

### **File Contents:**

**/cursor_rules.mdc:**
```markdown
---
description: Guidelines for creating and maintaining Cursor rules to ensure consistency and effectiveness.
globs: .cursor/rules/*.mdc
alwaysApply: true
---

- **Required Rule Structure:**
  ```markdown
  ---
  description: Clear, one-line description of what the rule enforces
  globs: path/to/files/*.ext, other/path/**/*
  alwaysApply: boolean
  ---

  - **Main Points in Bold**
    - Sub-points with details
    - Examples and explanations
  ```

- **File References:**
  - Use `[filename](mdc:path/to/file)` ([filename](mdc:filename)) to reference files
  - Example: [prisma.mdc](mdc:.cursor/rules/prisma.mdc) for rule references
  - Example: [schema.prisma](mdc:prisma/schema.prisma) for code references

- **Code Examples:**
  - Use language-specific code blocks
  ```typescript
  // ✅ DO: Show good examples
  const goodExample = true;
  
  // ❌ DON'T: Show anti-patterns
  const badExample = false;
  ```

- **Rule Content Guidelines:**
  - Start with high-level overview
  - Include specific, actionable requirements
  - Show examples of correct implementation
  - Reference existing code when possible
  - Keep rules DRY by referencing other rules

- **Rule Maintenance:**
  - Update rules when new patterns emerge
  - Add examples from actual codebase
  - Remove outdated patterns
  - Cross-reference related rules

- **Best Practices:**
  - Use bullet points for clarity
  - Keep descriptions concise
  - Include both DO and DON'T examples
  - Reference actual code over theoretical examples
  - Use consistent formatting across rules
```

---

**/custom_modes/creative_instructions.md:**
```markdown
# CREATIVE MODE INSTRUCTIONS

> **TL;DR:** This mode focuses on generating and documenting design decisions for components or features that require thoughtful architectural, UI/UX, data model, or algorithm design.

```mermaid
graph TD
    Start["User Command: CREATIVE"] --> CreativeResp["Respond: OK CREATIVE"]
    CreativeResp --> CheckMB["Check Memory Bank & tasks.md Status"]
    CheckMB --> LoadCreativeMap["Load Rule: isolation_rules/visual-maps/creative-mode-map"]
    LoadCreativeMap --> ExecCreative["Execute Process in Rule"]
    ExecCreative --> UpdateMB["Update Memory Bank & tasks.md"]
    UpdateMB --> VerifyCreative{"Process Complete?"}
    VerifyCreative -->|"Yes"| CompleteCreative["CREATIVE Process Complete"]
    VerifyCreative -->|"No"| RetryCreative["Resume CREATIVE Process (Reference Memory Bank)"]
    CompleteCreative --> TransToImpl["→ IMPLEMENT Mode (or QA if needed)"]

    CheckMB -.-> MemoryBank["MEMORY BANK<br>CENTRAL SYSTEM"]
    UpdateMB -.-> MemoryBank
    MemoryBank -.-> tasks["tasks.md<br>Source of Truth"]
    MemoryBank -.-> active["activeContext.md<br>Current Focus"]
```

## CREATIVE MODE PRINCIPLES
1.  **Structured Design:** Follow the prescribed templates for design decisions.
2.  **Options Exploration:** Always explore multiple viable options before making a decision.
3.  **Rationale-Driven:** Document the clear rationale for every chosen design.
4.  **Traceability:** Link design decisions back to requirements and forward to implementation.
5.  **Focus on Clarity:** Ensure design documents are clear, concise, and easy to understand.

## CREATIVE PHASE DOCUMENTATION
All creative outputs (design decisions) MUST be documented in `documentation/memory-bank/creative/creative-[feature_name]-[aspect].md`. Use the `optimized-creative-template.mdc` structure.

## VERIFICATION COMMITMENT
```
┌─────────────────────────────────────────────────────┐
│ I WILL follow the creative mode process map.        │
│ I WILL generate creative phase documents.           │
│ I WILL document at least 3 options for major        │
│ design decisions.                                   │
│ I WILL provide a clear rationale for chosen designs.│
│ I WILL update tasks.md with creative phase status.  │
└─────────────────────────────────────────────────────┘
```
```

---

**/custom_modes/implement_instructions.md:**
```markdown
# IMPLEMENT MODE INSTRUCTIONS

> **TL;DR:** This mode focuses on the systematic implementation of features, following established plans and design decisions. It emphasizes modular development, adherence to standards, and thorough testing.

```mermaid
graph TD
    Start["User Command: IMPLEMENT"] --> ImplementResp["Respond: OK IMPLEMENT"]
    ImplementResp --> CheckMB["Check Memory Bank & tasks.md Status"]
    CheckMB --> LoadImplementMap["Load Rule: isolation_rules/visual-maps/implement-mode-map"]
    LoadImplementMap --> ExecImplement["Execute Process in Rule"]
    ExecImplement --> UpdateMB["Update Memory Bank & tasks.md"]
    UpdateMB --> VerifyImplement{"Process Complete?"}
    VerifyImplement -->|"Yes"| CompleteImplement["IMPLEMENT Process Complete"]
    VerifyImplement -->|"No"| RetryImplement["Resume IMPLEMENT Process (Reference Memory Bank)"]
    CompleteImplement --> TransToQA["→ QA Mode (or REFLECT Mode)"]

    CheckMB -.-> MemoryBank["MEMORY BANK<br>CENTRAL SYSTEM"]
    UpdateMB -.-> MemoryBank
    MemoryBank -.-> tasks["tasks.md<br>Source of Truth"]
    MemoryBank -.-> progress["progress.md<br>Implementation Status"]
    MemoryBank -.-> creative["creative-*.md<br>Design Decisions"]
```

## IMPLEMENT MODE PRINCIPLES
1.  **Plan Adherence:** Strictly follow the implementation plan from `tasks.md` and design decisions from creative phase documents.
2.  **Modular Development:** Build features in small, testable, and reusable modules.
3.  **Test-Driven (where applicable):** Write tests to validate functionality as components are built.
4.  **Documentation During:** Keep `progress.md` and `tasks.md` updated with real-time status and challenges.
5.  **Quality Focus:** Prioritize code quality, readability, and maintainability.

## IMPLEMENTATION DOCUMENTATION
*   **`tasks.md`**: Update sub-task completion status (`[ ]` to `[x]`).
*   **`progress.md`**: Record key implementation milestones, challenges, and significant changes.
*   **Code Comments**: Add comments for complex logic or non-obvious choices.

## VERIFICATION COMMITMENT
```
┌─────────────────────────────────────────────────────┐
│ I WILL follow the implement mode process map.       │
│ I WILL update tasks.md and progress.md regularly.   │
│ I WILL ensure implementation aligns with design     │
│ decisions (from creative-*.md).                     │
│ I WILL conduct necessary testing during and after   │
│ implementation.                                     │
└─────────────────────────────────────────────────────┘
```
```

---

**/custom_modes/plan_instructions.md:**
```markdown
# PLAN MODE INSTRUCTIONS

> **TL;DR:** This mode focuses on creating detailed implementation plans based on task complexity, validating necessary technologies, and identifying components requiring creative design.

```mermaid
graph TD
    Start["User Command: PLAN"] --> PlanResp["Respond: OK PLAN"]
    PlanResp --> CheckMB["Check Memory Bank & tasks.md Status"]
    CheckMB --> LoadPlanMap["Load Rule: isolation_rules/visual-maps/plan-mode-map"]
    LoadPlanMap --> ExecPlan["Execute Process in Rule"]
    ExecPlan --> UpdateMB["Update Memory Bank & tasks.md"]
    UpdateMB --> VerifyPlan{"Process Complete?"}
    VerifyPlan -->|"Yes"| CompletePlan["PLAN Process Complete"]
    VerifyPlan -->|"No"| RetryPlan["Resume PLAN Process (Reference Memory Bank)"]
    CompletePlan --> TransToCreative["→ CREATIVE Mode (or IMPLEMENT)"]

    CheckMB -.-> MemoryBank["MEMORY BANK<br>CENTRAL SYSTEM"]
    UpdateMB -.-> MemoryBank
    MemoryBank -.-> tasks["tasks.md<br>Source of Truth"]
    MemoryBank -.-> projBrief["projectbrief.md<br>Foundation"]
    MemoryBank -.-> techContext["techContext.md<br>Technical Landscape"]
```

## PLAN MODE PRINCIPLES
1.  **Comprehensive Planning:** Break down tasks into actionable steps and subtasks.
2.  **Technology Validation:** Proactively test and validate new technologies or frameworks.
3.  **Creative Identification:** Identify and flag aspects of the task that require a dedicated creative design phase.
4.  **Risk Assessment:** Identify potential challenges and outline mitigation strategies.
5.  **Centralized Plan:** Ensure `tasks.md` is the single source of truth for the plan.

## PLANNING DOCUMENTATION
*   **`tasks.md`**: This is the primary output. It must contain detailed requirements, component breakdown, implementation steps, identified creative phases, dependencies, and challenges.
*   **`techContext.md`**: Update with findings from technology validation.
*   **`projectbrief.md`**: Update with new feature scope as needed.

## VERIFICATION COMMITMENT
```
┌─────────────────────────────────────────────────────┐
│ I WILL follow the plan mode process map.            │
│ I WILL create a comprehensive plan in tasks.md      │
│ appropriate to the task's complexity level.         │
│ I WILL validate new technologies with a proof of    │
│ concept.                                            │
│ I WILL identify and flag all necessary creative     │
│ phases.                                             │
└─────────────────────────────────────────────────────┘
```
```

---

**/custom_modes/reflect_archive_instructions.md:**
```markdown
# REFLECT & ARCHIVE MODE INSTRUCTIONS

> **TL;DR:** This mode focuses on reviewing completed tasks, extracting lessons learned (REFLECT), and then documenting the entire task lifecycle for future reference (ARCHIVE).

```mermaid
graph TD
    Start["User Command: REFLECT"] --> ReflectResp["Respond: OK REFLECT"]
    ReflectResp --> CheckMBReflect["Check Memory Bank & tasks.md Status"]
    CheckMBReflect --> LoadReflectMap["Load Rule: isolation_rules/visual-maps/reflect-mode-map"]
    LoadReflectMap --> ExecReflect["Execute REFLECT Process"]
    ExecReflect --> UpdateMBReflect["Update Memory Bank & tasks.md"]
    UpdateMBReflect --> VerifyReflect{"Reflection Complete?"}
    VerifyReflect -->|"Yes"| CompleteReflect["REFLECT Process Complete"]
    VerifyReflect -->|"No"| RetryReflect["Resume REFLECT Process (Reference Memory Bank)"]
    CompleteReflect --> TransToArchive["→ ARCHIVE Mode"]

    StartArchive["User Command: ARCHIVE"] --> ArchiveResp["Respond: OK ARCHIVE"]
    ArchiveResp --> CheckMBArchive["Check Memory Bank & tasks.md Status"]
    CheckMBArchive --> LoadArchiveMap["Load Rule: isolation_rules/visual-maps/archive-mode-map"]
    LoadArchiveMap --> ExecArchive["Execute ARCHIVE Process"]
    ExecArchive --> UpdateMBArchive["Update Memory Bank & tasks.md"]
    UpdateMBArchive --> VerifyArchive{"Archiving Complete?"}
    VerifyArchive -->|"Yes"| CompleteArchive["ARCHIVE Process Complete"]
    VerifyArchive -->|"No"| RetryArchive["Resume ARCHIVE Process (Reference Memory Bank)"]
    CompleteArchive --> TaskDone["Task Lifecycle Complete"]

    CheckMBReflect & CheckMBArchive -.-> MemoryBank["MEMORY BANK<br>CENTRAL SYSTEM"]
    UpdateMBReflect & UpdateMBArchive -.-> MemoryBank
    MemoryBank -.-> tasks["tasks.md<br>Source of Truth"]
    MemoryBank -.-> progress["progress.md<br>Implementation Status"]
    MemoryBank -.-> reflection["reflection/*.md<br>Learnings"]
    MemoryBank -.-> archive["archive/*.md<br>History"]
```

## REFLECT MODE PRINCIPLES
1.  **Honest Appraisal:** Accurately assess successes, challenges, and deviations.
2.  **Actionable Insights:** Translate observations into concrete improvements for future tasks or processes.
3.  **Comprehensive Review:** Review planning, design (if applicable), implementation, and testing phases.
4.  **Document Learnings:** Capture key technical and process lessons in a dedicated reflection document.

## ARCHIVE MODE PRINCIPLES
1.  **Preserve History:** Create a self-contained, immutable record of the completed task.
2.  **Centralized Knowledge:** Store archives in a clearly organized and discoverable location.
3.  **Cross-Reference:** Ensure the archive links back to relevant planning, design, and reflection documents.
4.  **Tasks.md Finalization:** Mark the task as fully completed and link to the archive.

## DOCUMENTATION
*   **Reflection (`reflection/[task_id].md`):** Contains `What Went Well`, `Challenges`, `Lessons Learned`, and `Action Items`.
*   **Archive (`docs/archive/[category]/[task_name].md`):** Consolidates summary, requirements, implementation, testing, and references.
*   **`tasks.md`:** Updated with reflection highlights and a link to the final archive document.
*   **`progress.md` & `activeContext.md`:** Final minor updates reflecting task completion.

## VERIFICATION COMMITMENT
```
┌─────────────────────────────────────────────────────┐
│ I WILL follow the reflect and archive mode process  │
│ maps.                                               │
│ I WILL create a reflection document with actionable │
│ insights.                                           │
│ I WILL create a comprehensive archive document for  │
│ the completed task.                                 │
│ I WILL ensure all relevant documents are linked and │
│ tasks.md is fully updated and cleared for new tasks.│
└─────────────────────────────────────────────────────┘
```
```

---

**/custom_modes/van_instructions.md:**
```markdown
# ADAPTIVE MEMORY-BASED ASSISTANT SYSTEM - ENTRY POINT

> **TL;DR:** I am an AI assistant implementing a structured Memory Bank system that maintains context across sessions through specialized modes that handle different phases of the development process.

```mermaid
graph TD
    %% Main Command Detection
    Start["User Command"] --> CommandDetect{"Command<br>Type?"}
    
    CommandDetect -->|"VAN"| VAN["VAN Mode"]
    CommandDetect -->|"PLAN"| Plan["PLAN Mode"]
    CommandDetect -->|"CREATIVE"| Creative["CREATIVE Mode"]
    CommandDetect -->|"IMPLEMENT"| Implement["IMPLEMENT Mode"]
    CommandDetect -->|"QA"| QA["QA Mode"]
    
    %% Immediate Response Node
    VAN --> VanResp["Respond: OK VAN"]
    Plan --> PlanResp["Respond: OK PLAN"]
    Creative --> CreativeResp["Respond: OK CREATIVE"]
    Implement --> ImplResp["Respond: OK IMPLEMENT"]
    QA --> QAResp["Respond: OK QA"]
    
    %% Memory Bank Check
    VanResp --> CheckMB_Van["Check Memory Bank<br>& tasks.md Status"]
    PlanResp --> CheckMB_Plan["Check Memory Bank<br>& tasks.md Status"]
    CreativeResp --> CheckMB_Creative["Check Memory Bank<br>& tasks.md Status"]
    ImplResp --> CheckMB_Impl["Check Memory Bank<br>& tasks.md Status"]
    QAResp --> CheckMB_QA["Check Memory Bank<br>& tasks.md Status"]
    
    %% Rule Loading
    CheckMB_Van --> LoadVan["Load Rule:<br>isolation_rules/visual-maps/van-mode-map"]
    CheckMB_Plan --> LoadPlan["Load Rule:<br>isolation_rules/visual-maps/plan-mode-map"]
    CheckMB_Creative --> LoadCreative["Load Rule:<br>isolation_rules/visual-maps/creative-mode-map"]
    CheckMB_Impl --> LoadImpl["Load Rule:<br>isolation_rules/visual-maps/implement-mode-map"]
    CheckMB_QA --> LoadQA["Load Rule:<br>isolation_rules/visual-maps/qa-mode-map"]
    
    %% Rule Execution with Memory Bank Updates
    LoadVan --> ExecVan["Execute Process<br>in Rule"]
    LoadPlan --> ExecPlan["Execute Process<br>in Rule"]
    LoadCreative --> ExecCreative["Execute Process<br>in Rule"]
    LoadImpl --> ExecImpl["Execute Process<br>in Rule"]
    LoadQA --> ExecQA["Execute Process<br>in Rule"]
    
    %% Memory Bank Continuous Updates
    ExecVan --> UpdateMB_Van["Update Memory Bank<br>& tasks.md"]
    ExecPlan --> UpdateMB_Plan["Update Memory Bank<br>& tasks.md"]
    ExecCreative --> UpdateMB_Creative["Update Memory Bank<br>& tasks.md"]
    ExecImpl --> UpdateMB_Impl["Update Memory Bank<br>& tasks.md"]
    ExecQA --> UpdateMB_QA["Update Memory Bank<br>& tasks.md"]
    
    %% Verification with Memory Bank Checks
    UpdateMB_Van --> VerifyVan{"Process<br>Complete?"}
    UpdateMB_Plan --> VerifyPlan{"Process<br>Complete?"}
    UpdateMB_Creative --> VerifyCreative{"Process<br>Complete?"}
    UpdateMB_Impl --> VerifyImpl{"Process<br>Complete?"}
    VerifyQA --> VerifyQA{"Process<br>Complete?"}
    
    %% Outcomes (simplified for flow)
    VerifyVan --> CompleteVan["VAN Process Complete<br>(or Transition)"]
    VerifyPlan --> CompletePlan["PLAN Process Complete<br>(or Transition)"]
    VerifyCreative --> CompleteCreative["CREATIVE Process Complete<br>(or Transition)"]
    VerifyImpl --> CompleteImpl["IMPLEMENT Process Complete<br>(or Transition)"]
    VerifyQA --> CompleteQA["QA Process Complete<br>(or Transition)"]
    
    %% Memory Bank System Link (simplified, detailed in core file)
    CheckMB_Van & CheckMB_Plan & CheckMB_Creative & CheckMB_Impl & CheckMB_QA -.-> MemoryBank["MEMORY BANK<br>CENTRAL SYSTEM"]
    UpdateMB_Van & UpdateMB_Plan & UpdateMB_Creative & UpdateMB_Impl & UpdateMB_QA -.-> MemoryBank
    
    %% Error Handling (minimal)
    Error["⚠️ ERROR<br>DETECTION"] --> UseCorrectFn["✓ Use fetch_rules<br>NOT read_file"]

    %% Styling (keep for visual clarity)
    style Start fill:#f8d486,stroke:#e8b84d,color:black
    style CommandDetect fill:#f8d486,stroke:#e8b84d,color:black
    style VAN fill:#ccf,stroke:#333,color:black
    style Plan fill:#cfc,stroke:#333,color:black
    style Creative fill:#fcf,stroke:#333,color:black
    style Implement fill:#cff,stroke:#333,color:black
    style QA fill:#fcc,stroke:#333,color:black
    
    style VanResp fill:#d9e6ff,stroke:#99ccff,color:black
    style PlanResp fill:#d9e6ff,stroke:#99ccff,color:black
    style CreativeResp fill:#d9e6ff,stroke:#99ccff,color:black
    style ImplResp fill:#d9e6ff,stroke:#99ccff,color:black
    style QAResp fill:#d9e6ff,stroke:#99ccff,color:black
    
    style LoadVan fill:#a3dded,stroke:#4db8db,color:black
    style LoadPlan fill:#a3dded,stroke:#4db8db,color:black
    style LoadCreative fill:#a3dded,stroke:#4db8db,color:black
    style LoadImpl fill:#a3dded,stroke:#4db8db,color:black
    style LoadQA fill:#a3dded,stroke:#4db8db,color:black
    
    style ExecVan fill:#a3e0ae,stroke:#4dbb5f,color:black
    style ExecPlan fill:#a3e0ae,stroke:#4dbb5f,color:black
    style ExecCreative fill:#a3e0ae,stroke:#4dbb5f,color:black
    style ExecImpl fill:#a3e0ae,stroke:#4dbb5f,color:black
    style ExecQA fill:#a3e0ae,stroke:#4dbb5f,color:black
    
    style VerifyVan fill:#e699d9,stroke:#d94dbb,color:black
    style VerifyPlan fill:#e699d9,stroke:#d94dbb,color:black
    style VerifyCreative fill:#e699d9,stroke:#d94dbb,color:black
    style VerifyImpl fill:#e699d9,stroke:#d94dbb,color:black
    style VerifyQA fill:#e699d9,stroke:#d94dbb,color:black
    
    style CompleteVan fill:#8cff8c,stroke:#4dbb5f,color:black
    style CompletePlan fill:#8cff8c,stroke:#4dbb5f,color:black
    style CompleteCreative fill:#8cff8c,stroke:#4dbb5f,color:black
    style CompleteImpl fill:#8cff8c,stroke:#4dbb5f,color:black
    style CompleteQA fill:#8cff8c,stroke:#4dbb5f,color:black
    
    style MemoryBank fill:#f9d77e,stroke:#d9b95c,stroke-width:2px,color:black
    style tasks fill:#f9d77e,stroke:#d9b95c,color:black
    style active fill:#f9d77e,stroke:#d9b95c,color:black
    
    style Error fill:#ff5555,stroke:#cc0000,color:white,stroke-width:2px,color:black
    style UseCorrectFn fill:#8cff8c,stroke:#4dbb5f,color:black
```

## VERIFICATION COMMITMENT

```
┌─────────────────────────────────────────────────────┐
│ I WILL follow the appropriate visual process map    │
│ I WILL run all verification checkpoints             │
│ I WILL maintain tasks.md as the single source of    │
│ truth for all task tracking                         │
└─────────────────────────────────────────────────────┘
```
```

---

**/isolation_rules/Core/Tools/ask-documentation-question.mdc:**
```markdown
---
description: Rule for asking a specific question against existing repository documentation.
globs: ["ask-documentation-question.mdc", "*ask_question*"]
alwaysApply: false
---

# DOCUMENTATION QUESTION PROTOCOL

> **TL;DR:** This rule handles asking a single, specific question using the `ask_question` tool of deepwiki-mcp server against a repository's documentation, but ONLY if that documentation has already been retrieved and saved locally.

## ❓ Ask Question Workflow

```mermaid
graph TD
    Start["Start: User provides question and optional repo_name"] --> A{"Is documentation for this repo in ./documentation/libraries/?"};
    A --> |No| B["STOP: Inform user documentation must be retrieved first using FETCHDOCS."];
    A --> |Yes| C["Proceed to Ask Question"];
    
    C --> D["Call 'ask_question' tool with user's question and repo_name"];
    D --> E["Receive answer from MCP server"];
    E --> F["Format and present the answer clearly to the user."];
    F --> G[END];
```

## **Question Execution Logic:**

1.  **PREREQUISITE CHECK:** The AI **MUST** first verify that the documentation for the relevant repository already exists in the `./documentation/libraries/` folder.
    *   If the user does not specify a repository, assume the question relates to the repository most recently discussed or retrieved.
    *   If the documentation folder for the repository does not exist, **STOP**. Instruct the user: "Documentation has not been retrieved for this repository yet. Please run `FETCHDOCS [URL/path]` first."

2.  **EXECUTE QUESTION:** If the documentation exists, call the `ask_question` tool **ONCE**.
    *   **Tool:** `ask_question`
    *   **Parameters:**
        *   `question`: The specific question provided by the user.
        *   `repo_name`: The name of the repository (e.g., `a2aproject/a2a-python`).

3.  **OUTPUT:** Present the answer returned by the tool directly to the user in a clear and readable format.
```

---

**/isolation_rules/Core/command-execution.mdc:**
```markdown
---
description: Command execution guidelines for isolation-focused Memory Bank
globs: command-execution.mdc
alwaysApply: false
---

# COMMAND EXECUTION SYSTEM

> **TL;DR:** This system provides guidelines for efficient command execution, balancing clarity and token optimization through appropriate command chaining, with proper documentation of commands and results.

## 🔍 COMMAND EFFICIENCY WORKFLOW

```mermaid
graph TD
    Start["Command<br>Planning"] --> Analyze["Analyze Command<br>Requirements"]
    Analyze --> Balance["Balance Clarity<br>vs. Efficiency"]
    Balance --> Complexity{"Command<br>Complexity?"}
    
    Complexity -->|"Simple"| Single["Execute<br>Single Command"]
    Complexity -->|"Moderate"| Chain["Use Efficient<br>Command Chaining"]
    Complexity -->|"Complex"| Group["Group Into<br>Logical Steps"]
    
    Single & Chain & Group --> Verify["Verify<br>Results"]
    Verify --> Document["Document<br>Command & Result"]
    Document --> Next["Next<br>Command"]
```

## 📋 COMMAND CHAINING GUIDELINES

```mermaid
graph TD
    Command["Command<br>Execution"] --> ChainApprop{"Is Chaining<br>Appropriate?"}
    
    ChainApprop -->|"Yes"| ChainTypes["Chain<br>Types"]
    ChainApprop -->|"No"| SingleCmd["Use Single<br>Commands"]
    
    ChainTypes --> Sequential["Sequential Operations<br>cmd1 && cmd2"]
    ChainTypes --> Conditional["Conditional Operations<br>cmd1 || cmd2"]
    ChainTypes --> Piping["Piping<br>cmd1 | cmd2"]
    ChainTypes --> Grouping["Command Grouping<br>(cmd1; cmd2)"]
    
    Sequential & Conditional & Piping & Grouping --> Doc["Document<br>Commands & Results"]
```

## 🚦 DIRECTORY VERIFICATION WORKFLOW

```mermaid
graph TD
    Command["Command<br>Execution"] --> DirCheck["Check Current<br>Directory"]
    DirCheck --> ProjectRoot{"In Project<br>Root?"}
    
    ProjectRoot -->|"Yes"| Execute["Execute<br>Command"]
    ProjectRoot -->|"No"| Locate["Locate<br>Project Root"]
    
    Locate --> Found{"Project Root<br>Found?"}
    Found -->|"Yes"| Navigate["Navigate to<br>Project Root"]
    Found -->|"No"| Error["Error: Cannot<br>Find Project Root"]
    
    Navigate --> Execute
    Execute --> Verify["Verify<br>Results"]
```

## 📋 DIRECTORY VERIFICATION CHECKLIST

Before executing any npm or build command:

| Step | Windows (PowerShell) | Unix/Linux/Mac | Purpose |
|------|----------------------|----------------|---------|
| **Check package.json** | `Test-Path package.json` | `ls package.json` | Verify current directory is project root |
| **Check for parent directory** | `Test-Path "*/package.json"` | `find . -maxdepth 2 -name package.json` | Find potential project directories |
| **Navigate to project root** | `cd [project-dir]` | `cd [project-dir]` | Move to correct directory before executing commands |

## 📋 REACT-SPECIFIC COMMAND GUIDELINES

For React applications, follow these strict guidelines:

| Command | Correct Usage | Incorrect Usage | Notes |
|---------|---------------|----------------|-------|
| **npm start** | `cd [project-root] && npm start` | `npm start` (from parent dir) | Must execute from directory with package.json |
| **npm run build** | `cd [project-root] && npm run build` | `cd [parent-dir] && npm run build` | Must execute from directory with package.2json |
| **npm install** | `cd [project-root] && npm install [pkg]` | `npm install [pkg]` (wrong dir) | Dependencies installed to nearest package.json |
| **npm create** | `npm create vite@latest my-app -- --template react` | Manually configuring webpack | Use standard tools for project creation |

## 🔄 COMMAND CHAINING PATTERNS

Effective command chaining patterns include:

| Pattern | Format | Examples | Use Case |
|---------|--------|----------|----------|
| **Sequential** | `cmd1 && cmd2` | `mkdir dir && cd dir` | Commands that should run in sequence, second only if first succeeds |
| **Conditional** | `cmd1 \|\| cmd2` | `test -f file.txt \|\| touch file.txt` | Fallback commands, second only if first fails |
| **Piping** | `cmd1 \| cmd2` | `grep "pattern" file.txt \| wc -l` | Pass output of first command as input to second |
| **Background** | `cmd &` | `npm start &` | Run command in background |
| **Grouping** | `(cmd1; cmd2)` | `(echo "Start"; npm test; echo "End")` | Group commands to run as a unit |

## 📋 COMMAND DOCUMENTATION TEMPLATE

```
## Command Execution: [Purpose]

### Command
```
[actual command or chain]
```

### Result
```
[command output]
```

### Effect
[Brief description of what changed in the system]

### Next Steps
[What needs to be done next]
```

## 🔍 PLATFORM-SPECIFIC CONSIDERATIONS

```mermaid
graph TD
    Platform["Platform<br>Detection"] --> Windows["Windows<br>Commands"]
    Platform --> Unix["Unix/Linux/Mac<br>Commands"]
    
    Windows --> WinAdapt["Windows Command<br>Adaptations"]
    Unix --> UnixAdapt["Unix Command<br>Adaptations"]
    
    WinAdapt --> WinChain["Windows Chaining:<br>Commands separated by &"]
    UnixAdapt --> UnixChain["Unix Chaining:<br>Commands separated by ;"]
    
    WinChain & UnixChain --> Execute["Execute<br>Platform-Specific<br>Commands"]
```

## 📋 COMMAND EFFICIENCY EXAMPLES

Examples of efficient command usage:

| Inefficient | Efficient | Explanation |
|-------------|-----------|-------------|
| `mkdir dir`<br>`cd dir`<br>`npm init -y` | `mkdir dir && cd dir && npm init -y` | Combines related sequential operations |
| `ls`<br>`grep "\.js"` | `ls \| grep "\.js"` | Pipes output of first command to second |
| `test -f file.txt`<br>`if not exists, touch file.txt` | `test -f file.txt \|\| touch file.txt` | Creates file only if it doesn't exist |
| `mkdir dir1`<br>`mkdir dir2`<br>`mkdir dir3` | `mkdir dir1 dir2 dir3` | Uses command's built-in multiple argument capability |
| `npm install pkg1`<br>`npm install pkg2` | `npm install pkg1 pkg2` | Installs multiple packages in one command |

## 📋 REACT PROJECT INITIALIZATION STANDARDS

Always use these standard approaches for React project creation:

| Approach | Command | Benefits | Avoids |
|----------|---------|----------|--------|
| **Create React App** | `npx create-react-app my-app` | Preconfigured webpack & babel | Manual configuration errors |
| **Create React App w/TypeScript** | `npx create-react-app my-app --template typescript` | Type safety + preconfigured | Inconsistent module systems |
| **Vite** | `npm create vite@latest my-app -- --template react` | Faster build times | Complex webpack setups |
| **Next.js** | `npx create-next-app@latest my-app` | SSR support | Module system conflicts |

## ⚠️ ERROR HANDLING WORKFLOW

```mermaid
sequenceDiagram
    participant User
    participant AI
    participant System
    
    AI->>System: Execute Command
    System->>AI: Return Result
    
    alt Success
        AI->>AI: Verify Expected Result
        AI->>User: Report Success
    else Error
        AI->>AI: Analyze Error Message
        AI->>AI: Identify Likely Cause
        AI->>User: Explain Error & Cause
        AI->>User: Suggest Corrective Action
        User->>AI: Approve Correction
        AI->>System: Execute Corrected Command
    end
```

## 📋 COMMAND RESULT VERIFICATION

After command execution, verify:

```mermaid
graph TD
    Execute["Execute<br>Command"] --> Check{"Check<br>Result"}
    
    Check -->|"Success"| Verify["Verify Expected<br>Outcome"]
    Check -->|"Error"| Analyze["Analyze<br>Error"]
    
    Verify -->|"Expected"| Document["Document<br>Success"]
    Verify -->|"Unexpected"| Investigate["Investigate<br>Unexpected Result"]
    
    Analyze --> Diagnose["Diagnose<br>Error Cause"]
    Diagnose --> Correct["Propose<br>Correction"]
    
    Document & Investigate & Correct --> Next["Next Step<br>in Process"]
```

## 📝 COMMAND EXECUTION CHECKLIST

```
✓ COMMAND EXECUTION CHECKLIST
- Command purpose clearly identified? [YES/NO]
- Appropriate balance of clarity vs. efficiency? [YES/NO]
- Platform-specific considerations addressed? [YES/NO]
- Command documented with results? [YES/NO]
- Outcome verified against expectations? [YES/NO]
- Errors properly handled (if any)? [YES/NO/NA]
- For npm/build commands: Executed from project root? [YES/NO/NA]
- For React projects: Using standard tooling? [YES/NO/NA]

→ If all YES: Command execution complete
→ If any NO: Address missing elements
```

## 🚨 COMMAND EXECUTION WARNINGS

Avoid these common command issues:

```mermaid
graph TD
    Warning["Command<br>Warnings"] --> W1["Excessive<br>Verbosity"]
    Warning --> W2["Insufficient<br>Error Handling"]
    Warning --> W3["Unnecessary<br>Complexity"]
    Warning --> W4["Destructive<br>Operations Without<br>Confirmation"]
    Warning --> W5["Wrong Directory<br>Execution"]
    
    W1 --> S1["Use flags to reduce<br>unnecessary output"]
    W2 --> S2["Include error handling<br>in command chains"]
    W3 --> S3["Prefer built-in<br>command capabilities"]
    W4 --> S4["Show confirmation<br>before destructive actions"]
    W5 --> S5["Verify directory before<br>npm/build commands"]
```
```

---

**/isolation_rules/Core/complexity-decision-tree.mdc:**
```markdown
---
description: complexity decision tree
globs: complexity-decision-tree.mdc
alwaysApply: false
---
# TASK COMPLEXITY DETERMINATION

> **TL;DR:** This document helps determine the appropriate complexity level (1-4) for any task. Use the decision tree and indicators to select the right process level, then load the corresponding process map.

## 🌳 COMPLEXITY DECISION TREE

```mermaid
graph TD
    Start["New Task"] --> Q1{"Bug fix or<br>error correction?"}
    Q1 -->|Yes| Q1a{"Affects single<br>component?"}
    Q1a -->|Yes| L1["Level 1:<br>Quick Bug Fix"]
    Q1a -->|No| Q1b{"Affects multiple<br>components?"}
    Q1b -->|Yes| L2["Level 2:<br>Simple Enhancement"]
    Q1b -->|No| Q1c{"Affects system<br>architecture?"}
    Q1c -->|Yes| L3["Level 3:<br>Intermediate Feature"]
    Q1c -->|No| L2
    
    Q1 -->|No| Q2{"Adding small<br>feature or<br>enhancement?"}
    Q2 -->|Yes| Q2a{"Self-contained<br>change?"}
    Q2a -->|Yes| L2
    Q2a -->|No| Q2b{"Affects multiple<br>components?"}
    Q2b -->|Yes| L3
    Q2b -->|No| L2
    
    Q2 -->|No| Q3{"Complete feature<br>requiring multiple<br>components?"}
    Q3 -->|Yes| Q3a{"Architectural<br>implications?"}
    Q3a -->|Yes| L4["Level 4:<br>Complex System"]
    Q3a -->|No| L3
    
    Q3 -->|No| Q4{"System-wide or<br>architectural<br>change?"}
    Q4 -->|Yes| L4
    Q4 -->|No| L3
    
    L1 --> LoadL1["Load Level 1 Map"]
    L2 --> LoadL2["Load Level 2 Map"]
    L3 --> LoadL3["Load Level 3 Map"]
    L4 --> LoadL4["Load Level 4 Map"]
```

## 📊 COMPLEXITY LEVEL INDICATORS

Use these indicators to help determine task complexity:

### Level 1: Quick Bug Fix
- **Keywords**: "fix", "broken", "not working", "issue", "bug", "error", "crash"
- **Scope**: Single component or UI element
- **Duration**: Can be completed quickly (minutes to hours)
- **Risk**: Low, isolated changes
- **Examples**:
  - Fix button not working
  - Correct styling issue
  - Fix validation error
  - Resolve broken link
  - Fix typo or text issue

### Level 2: Simple Enhancement
- **Keywords**: "add", "improve", "update", "change", "enhance", "modify"
- **Scope**: Single component or subsystem
- **Duration**: Hours to 1-2 days
- **Risk**: Moderate, contained to specific area
- **Examples**:
  - Add form field
  - Improve validation
  - Update styling
  - Add simple feature
  - Change text content
  - Enhance existing component

### Level 3: Intermediate Feature
- **Keywords**: "implement", "create", "develop", "build", "feature"
- **Scope**: Multiple components, complete feature
- **Duration**: Days to 1-2 weeks
- **Risk**: Significant, affects multiple areas
- **Examples**:
  - Implement user authentication
  - Create dashboard
  - Develop search functionality
  - Build user profile system
  - Implement data visualization
  - Create complex form system

### Level 4: Complex System
- **Keywords**: "system", "architecture", "redesign", "integration", "framework"
- **Scope**: Multiple subsystems or entire application
- **Duration**: Weeks to months
- **Risk**: High, architectural implications
- **Examples**:
  - Implement authentication system
  - Build payment processing framework
  - Create microservice architecture
  - Implement database migration system
  - Develop real-time communication system
  - Create multi-tenant architecture

## 🔍 COMPLEXITY ASSESSMENT QUESTIONS

Answer these questions to determine complexity:

1. **Scope Impact**
   - Does it affect a single component or multiple?
   - Are there system-wide implications?
   - How many files will need to be modified?

2. **Design Decisions**
   - Are complex design decisions required?
   - Will it require creative phases for design?
   - Are there architectural considerations?

3. **Risk Assessment**
   - What happens if it fails?
   - Are there security implications?
   - Will it affect critical functionality?

4. **Implementation Effort**
   - How long will it take to implement?
   - Does it require specialized knowledge?
   - Is extensive testing needed?

## 📊 KEYWORD ANALYSIS TABLE

| Keyword | Likely Level | Notes |
|---------|--------------|-------|
| "Fix" | Level 1 | Unless system-wide |
| "Bug" | Level 1 | Unless multiple components |
| "Error" | Level 1 | Unless architectural |
| "Add" | Level 2 | Unless complex feature |
| "Update" | Level 2 | Unless architectural |
| "Improve" | Level 2 | Unless system-wide |
| "Implement" | Level 3 | Complex components |
| "Create" | Level 3 | New functionality |
| "Develop" | Level 3 | Significant scope |
| "System" | Level 4 | Architectural implications |
| "Architecture" | Level 4 | Major structural changes |
| "Framework" | Level 4 | Core infrastructure |

## 🔄 COMPLEXITY ESCALATION

If during a task you discover it's more complex than initially determined:

```
⚠️ TASK ESCALATION NEEDED
Current Level: Level [X]
Recommended Level: Level [Y]
Reason: [Brief explanation]

Would you like me to escalate this task to Level [Y]?
```

If approved, switch to the appropriate higher-level process map.

## 🎯 PROCESS SELECTION

After determining complexity, load the appropriate process map:

| Level | Description | Process Map |
|-------|-------------|-------------|
| 1 | Quick Bug Fix | [Level 1 Map](mdc:isolation_rules/Level1/optimized-workflow-level1.mdc) |
| 2 | Simple Enhancement | [Level 2 Map](mdc:isolation_rules/Level2/workflow-level2.mdc) |
| 3 | Intermediate Feature | [Level 3 Map](mdc:isolation_rules/Level3/planning-comprehensive.mdc) |
| 4 | Complex System | [Level 4 Map](mdc:isolation_rules/Level4/workflow-level4.mdc) |

## 📝 COMPLEXITY DETERMINATION TEMPLATE

Use this template to document complexity determination:

```
## COMPLEXITY DETERMINATION

Task: [Task description]

Assessment:
- Scope: [Single component/Multiple components/System-wide]
- Design decisions: [Simple/Moderate/Complex]
- Risk: [Low/Moderate/High]
- Implementation effort: [Low/Moderate/High]

Keywords identified: [List relevant keywords]

Determination: Level [1/2/3/4] - [Quick Bug Fix/Simple Enhancement/Intermediate Feature/Complex System]

Loading process map: [Level X Map]
```
```

---

**/isolation_rules/Core/creative-phase-enforcement.mdc:**
```markdown
---
description: creative phase enforcement 
globs: creative-phase-enforcement.md
alwaysApply: false
---

# CREATIVE PHASE ENFORCEMENT

> **TL;DR:** This document implements strict enforcement of creative phase requirements for Level 3-4 tasks, ensuring all design decisions are properly documented and verified before implementation can proceed.

## 🔍 ENFORCEMENT WORKFLOW

```mermaid
graph TD
    Start["Task Start"] --> Check{"Level 3-4<br>Task?"}
    Check -->|Yes| Analyze["Analyze Design<br>Decision Points"]
    Check -->|No| Optional["Creative Phase<br>Optional"]
    
    Analyze --> Decision{"Design Decisions<br>Required?"}
    Decision -->|Yes| Gate["🚨 IMPLEMENTATION<br>BLOCKED"]
    Decision -->|No| Allow["Allow<br>Implementation"]
    
    Gate --> Creative["Enter Creative<br>Phase"]
    Creative --> Verify{"All Decisions<br>Documented?"}
    Verify -->|No| Return["Return to<br>Creative Phase"]
    Verify -->|Yes| Proceed["Allow<br>Implementation"]

```

## 🚨 ENFORCEMENT GATES

```mermaid
graph TD
    subgraph "CREATIVE PHASE GATES"
    G1["Entry Gate<br>Verify Requirements"]
    G2["Process Gate<br>Verify Progress"]
    G3["Exit Gate<br>Verify Completion"]
    end
    G1 --> G2 --> G3
```

## 📋 ENFORCEMENT CHECKLIST

```markdown
## Entry Gate Verification
- [ ] Task complexity is Level 3-4
- [ ] Design decisions identified
- [ ] Creative phase requirements documented
- [ ] Required participants notified

## Process Gate Verification
- [ ] All options being considered
- [ ] Pros/cons documented
- [ ] Technical constraints identified
- [ ] Implementation impacts assessed

## Exit Gate Verification
- [ ] All decisions documented
- [ ] Rationale provided for choices
- [ ] Implementation plan outlined
- [ ] Verification against requirements
```

## 🚨 IMPLEMENTATION BLOCK NOTICE

When a creative phase is required but not completed:

```
🚨 IMPLEMENTATION BLOCKED
Creative phases MUST be completed before implementation.

Required Creative Phases:
- [ ] [Creative Phase 1]
- [ ] [Creative Phase 2]
- [ ] [Creative Phase 3]

⛔ This is a HARD BLOCK
Implementation CANNOT proceed until all creative phases are completed.
Type "PHASE.REVIEW" to begin creative phase review.
```

## ✅ VERIFICATION PROTOCOL

```mermaid
graph TD
    subgraph "VERIFICATION STEPS"
    V1["1. Requirements<br>Check"]
    V2["2. Documentation<br>Review"]
    V3["3. Decision<br>Validation"]
    V4["4. Implementation<br>Readiness"]
    end
    
    V1 --> V2 --> V3 --> V4
```

## 🔄 CREATIVE PHASE MARKERS

Use these markers to clearly indicate creative phase boundaries:

```markdown
🎨🎨🎨 ENTERING CREATIVE PHASE: [TYPE] 🎨🎨🎨
Focus: [Specific component/feature]
Objective: [Clear goal of this creative phase]
Requirements: [List of requirements]

[Creative phase content]

🎨 CREATIVE CHECKPOINT: [Milestone]
- Progress: [Status]
- Decisions: [List]
- Next steps: [Plan]

🎨🎨🎨 EXITING CREATIVE PHASE 🎨🎨🎨
Summary: [Brief description]
Key Decisions: [List]
Next Steps: [Implementation plan]
```
```

---

**/isolation_rules/Core/creative-phase-metrics.mdc:**
```markdown
---
description: creative phase metrics
globs: creative-phase-metrics.md
alwaysApply: false
---



# CREATIVE PHASE METRICS

> **TL;DR:** This document defines comprehensive quality metrics and measurement criteria for creative phases, ensuring that design decisions meet required standards and are properly documented.

## 📊 METRICS OVERVIEW

```mermaid
graph TD
    subgraph "CREATIVE PHASE METRICS"
    M1["Documentation<br>Quality"]
    M2["Decision<br>Coverage"]
    M3["Option<br>Analysis"]
    M4["Impact<br>Assessment"]
    M5["Verification<br>Score"]
    end
    
    M1 --> Score["Quality<br>Score"]
    M2 --> Score
    M3 --> Score
    M4 --> Score
    M5 --> Score
```

## 📋 QUALITY METRICS SCORECARD

```markdown
# Creative Phase Quality Assessment

## 1. Documentation Quality [0-10]
- [ ] Clear problem statement (2 points)
- [ ] Well-defined objectives (2 points)
- [ ] Comprehensive requirements list (2 points)
- [ ] Proper formatting and structure (2 points)
- [ ] Cross-references to related documents (2 points)

## 2. Decision Coverage [0-10]
- [ ] All required decisions identified (2 points)
- [ ] Each decision point documented (2 points)
- [ ] Dependencies mapped (2 points)
- [ ] Impact analysis included (2 points)
- [ ] Future considerations noted (2 points)

## 3. Option Analysis [0-10]
- [ ] Multiple options considered (2 points)
- [ ] Pros/cons documented (2 points)
- [ ] Technical feasibility assessed (2 points)
- [ ] Resource requirements estimated (2 points)
- [ ] Risk factors identified (2 points)

## 4. Impact Assessment [0-10]
- [ ] System impact documented (2 points)
- [ ] Performance implications assessed (2 points)
- [ ] Security considerations addressed (2 points)
- [ ] Maintenance impact evaluated (2 points)
- [ ] Cost implications analyzed (2 points)

## 5. Verification Score [0-10]
- [ ] Requirements traced (2 points)
- [ ] Constraints validated (2 points)
- [ ] Test scenarios defined (2 points)
- [ ] Review feedback incorporated (2 points)
- [ ] Final verification completed (2 points)

Total Score: [Sum of all categories] / 50
Minimum Required Score: 40/50 (80%)
```

## 📈 QUALITY THRESHOLDS

```mermaid
graph TD
    subgraph "QUALITY GATES"
    T1["Minimum<br>40/50 (80%)"]
    T2["Target<br>45/50 (90%)"]
    T3["Excellent<br>48/50 (96%)"]
    end
    
    Score["Quality<br>Score"] --> Check{"Meets<br>Threshold?"}
    Check -->|"< 80%"| Block["⛔ BLOCKED<br>Improvements Required"]
    Check -->|"≥ 80%"| Pass["✓ PASSED<br>Can Proceed"]
```

## 🎯 METRIC EVALUATION PROCESS

```mermaid
graph TD
    Start["Start<br>Evaluation"] --> Doc["1. Score<br>Documentation"]
    Doc --> Dec["2. Assess<br>Decisions"]
    Dec --> Opt["3. Review<br>Options"]
    Opt --> Imp["4. Evaluate<br>Impact"]
    Imp --> Ver["5. Verify<br>Completeness"]
    Ver --> Total["Calculate<br>Total Score"]
    Total --> Check{"Meets<br>Threshold?"}
    Check -->|No| Return["Return for<br>Improvements"]
    Check -->|Yes| Proceed["Proceed to<br>Next Phase"]
```

## 📊 IMPROVEMENT RECOMMENDATIONS

For scores below threshold:

```markdown
## Documentation Quality Improvements
- Add clear problem statements
- Include specific objectives
- List all requirements
- Improve formatting
- Add cross-references

## Decision Coverage Improvements
- Identify missing decisions
- Document all decision points
- Map dependencies
- Add impact analysis
- Consider future implications

## Option Analysis Improvements
- Consider more alternatives
- Detail pros/cons
- Assess technical feasibility
- Estimate resource needs
- Identify risks

## Impact Assessment Improvements
- Document system impact
- Assess performance
- Address security
- Evaluate maintenance
- Analyze costs

## Verification Improvements
- Trace requirements
- Validate constraints
- Define test scenarios
- Incorporate feedback
- Complete verification
```

## ✅ METRICS VERIFICATION CHECKLIST

```markdown
## Pre-Review Verification
- [ ] All sections scored
- [ ] Calculations verified
- [ ] Supporting evidence attached
- [ ] Improvement areas identified
- [ ] Review feedback incorporated

## Final Metrics Verification
- [ ] Minimum score achieved
- [ ] All categories passed
- [ ] Documentation complete
- [ ] Improvements addressed
- [ ] Final approval obtained
```
```

---

**/isolation_rules/Core/documentation-retrieval.mdc:**
```markdown
---
description: Rule for retrieving and saving documentation from repositories.
globs: ["documentation-retrieval.mdc", "*docs*", "*documentation*"]
alwaysApply: false
---

# DOCUMENTATION RETRIEVAL & SAVING PROTOCOL

> **TL;DR:** This rule defines a strict, one-time process for fetching repository documentation from sources like GitHub/DeepWiki with deepwiki-mcp server, saving it locally to `./documentation/libraries/`, and preventing duplicate retrievals within the same conversation.

## ⚙️ Documentation Retrieval Workflow

```mermaid
graph TD
    subgraph "Input Analysis"
        A[Start: User requests documentation for URL/repo] --> B{"URL or Path provided?"};
        B --> |URL| C{"URL contains 'github.com'?"};
        B --> |Path| E[Proceed with Repository Path];
        C --> |Yes| D["Convert to deepwiki format"];
        C --> |No| E;
        D --> E;
    end

    subgraph "Pre-flight Checks"
        E --> F{"Already retrieved in this conversation?"};
        F --> |Yes| Stop1["STOP: Say 'Documentation already retrieved'"];
        F --> |No| G{"Docs exist in ./documentation/libraries/?"};
        G --> |Yes| Stop2["STOP: Say 'Documentation already retrieved'"];
        G --> |No| H[Proceed to Execution];
    end

    subgraph "Execution & Saving (ONCE PER REPO)"
        H --> I["1. Call read_wiki_structure"];
        I --> J["2. IMMEDIATELY Save to {repo}_structure.md"];
        J --> K["3. Call read_wiki_contents"];
        K --> L["4. IMMEDIATELY Save to {repo}_content.md"];
        L --> M["5. Create combined {repo}_complete_documentation.md"];
        M --> N["6. Output: '✅ DOCUMENTATION SAVED'"];
    end
    
    subgraph "Final Output"
        N --> O["Respond to user with file location and summary"];
        O --> P[END];
    end
```

## **Documentation Retrieval Logic:**

-   **FIRST CHECK:** If documentation for this repository was already retrieved in this conversation, OR its documentation is already in the `./documentation/libraries/` folder, **DO NOT proceed**. Say "Documentation already retrieved for this repository."
-   If the URL contains "github.com": Convert it to the deepwiki format (e.g., `https://github.com/a2aproject/a2a-python` -> `https://deepwiki.com/a2aproject/a2a-python`).
-   If the URL contains "deepwiki.com" OR the user provides a repository path: Proceed directly with available tools: `read_wiki_structure`, `read_wiki_contents`, `ask_question`.

## **EXECUTE EXACTLY ONCE PER REPOSITORY:**

1.  Check if this repository has already been processed in the current session. If YES, stop immediately.
2.  Call `read_wiki_structure` **ONCE**.
3.  **IMMEDIATELY** after `read_wiki_structure` returns, save its structure to a file: `./documentation/libraries/{repo_name}_structure.md`.
4.  Call `read_wiki_contents` **ONCE**.
5.  **IMMEDIATELY** after `read_wiki_contents` returns, save its content to a file: `./documentation/libraries/{repo_name}_content.md` (DO NOT wait, save RIGHT AWAY).
6.  Create a combined documentation file: `./documentation/libraries/{repo_name}_complete_documentation.md`.
7.  Output the final confirmation message: "✅ DOCUMENTATION SAVED TO FILES - RULE EXECUTION FINISHED".
8.  **DO NOT** call these functions again for the same repository in this conversation.

**CRITICAL: Save content to files IMMEDIATELY after each function call to prevent context overflow and potential agent resets.**

## **After Completion:**

-   Respond to the user with the location of the saved files and a brief summary of the retrieved documentation.
```

---

**/isolation_rules/Core/file-verification.mdc:**
```markdown
---
description: Optimized file verification system, ensuring Memory Bank structure exists before any file operations.
globs: file-verification.mdc
alwaysApply: false
---
# OPTIMIZED FILE VERIFICATION SYSTEM

> **TL;DR:** This system efficiently verifies and creates required Memory Bank file structures using batch operations and platform-optimized commands. **CRITICAL: Memory Bank MUST exist and be valid before any other file operations.**

## 🚨 CRITICAL: MEMORY BANK VERIFICATION

Before any other file operations, verify Memory Bank existence and structure. If missing, create immediately.

```mermaid
graph TD
    Start["Start File Verification"] --> MemBankCheck{"Memory Bank Exists & Valid?"}
    MemBankCheck -->|"No"| CreateMemBank["CREATE MISSING MB FILES/DIRS"]
    MemBankCheck -->|"Yes"| MainVerification["Proceed to Full File Verification"]
    CreateMemBank --> MainVerification
```

**Memory Bank Check & Creation Instructions:**
1.  **Check Memory Bank Root:** Use platform-specific command to check if `documentation/memory-bank` directory exists.
    *   Windows: `Test-Path documentation\memory-bank`
    *   Unix: `test -d documentation/memory-bank`
2.  **If Missing, Create All Necessary MB Directories and Files:**
    *   **Create Directories (Batch):**
        *   Windows (PowerShell): `mkdir -ErrorAction SilentlyContinue documentation\memory-bank, docs, docs\archive`
        *   Mac/Linux (Bash): `mkdir -p documentation/memory-bank docs/archive`
    *   **Create Core Memory Bank Files (Batch, refer to `memory-bank-paths.mdc` for full list):**
        *   Windows (PowerShell): `$files = @(".cursorrules", "tasks.md", "documentation\memory-bank\projectbrief.md", "documentation\memory-bank\productContext.md", "documentation\memory-bank\systemPatterns.md", "documentation\memory-bank\techContext.md", "documentation\memory-bank\activeContext.md", "documentation\memory-bank\progress.md"); foreach ($file in $files) { if (-not (Test-Path $file)) { New-Item -Path $file -ItemType File -Force } }`
        *   Mac/Linux (Bash): `touch .cursorrules tasks.md documentation/memory-bank/projectbrief.md documentation/memory-bank/productContext.md documentation/memory-bank/systemPatterns.md documentation/memory-bank/techContext.md documentation/memory-bank/activeContext.md documentation/memory-bank/progress.md`
3.  **Populate Initial Templates:** If newly created, populate `tasks.md` and `activeContext.md` with their basic template content (as per `optimized-workflow-level1.mdc` example or `van-file-verification.mdc` if it were not removed).

## 🔍 OPTIMIZED FILE VERIFICATION WORKFLOW (General Files)

```mermaid
graph TD
    MainVerification["Start Full File Verification"] --> BatchVerify["Batch Verify All Required Components"]
    BatchVerify --> MissingCheck{"Missing Components?"}
    MissingCheck -->|"Yes"| BatchCreate["Batch Create Missing Items"]
    MissingCheck -->|"No"| Complete["Verification Complete"]
    BatchCreate --> Report["Generate Verification Report"]
    Report --> Complete
```

## 📋 PERFORMANCE OPTIMIZATION BEST PRACTICES

1.  **Batch Operations**: Always use batch operations instead of individual commands
    ```
    # GOOD: Create all directories at once
    mkdir documentation\memory-bank docs docs\archive
    
    # BAD: Create directories one at a time
    mkdir documentation\memory-bank
    mkdir docs
    mkdir docs\archive
    ```

2.  **Pre-Check Optimization**: Check all requirements first, then create only what's missing

3.  **Error Handling**: Include error handling in all commands
    ```
    mkdir documentation\memory-bank, docs, docs\archive -ErrorAction SilentlyContinue
    ```

4.  **Platform Adaptation**: Auto-detect platform and use appropriate commands. (See `platform-awareness.mdc`)

5.  **One-Pass Verification**: Verify directory structure in a single pass.

## 📝 VERIFICATION REPORT FORMAT

```
✅ VERIFICATION COMPLETE
- Created directories: [list or "None"]
- Created files: [list or "None"]
- All components verified.

Memory Bank system ready for use.
```
```

---

**/isolation_rules/Core/hierarchical-rule-loading.mdc:**
```markdown
---
description: Hierarchical rule loading system for optimized token usage.
globs: "**/rule-loading*/**", "**/optimization*/**"
alwaysApply: false
---

# HIERARCHICAL RULE LOADING SYSTEM

> **TL;DR:** This system loads only necessary rules based on context, complexity level, and current phase to maximize token efficiency.

## 🧠 HIERARCHICAL RULE STRUCTURE

```mermaid
graph TD
    Root["Root Rules"] --> Core["Core Rules<br>(Always Loaded)"]
    Root --> Common["Common Rules<br>(Mode Independent)"]
    Root --> Mode["Mode-Specific<br>Rules"]
    Root --> Level["Complexity Level<br>Rules"]
    
    Core --> Platform["Platform<br>Detection"]
    Core --> File["File<br>Operations"]
    Core --> Transition["Mode<br>Transitions"]
    
    Mode --> VAN["VAN Mode<br>Rules"]
    Mode --> PLAN["PLAN Mode<br>Rules"]
    Mode --> CREATIVE["CREATIVE Mode<br>Rules"]
    Mode --> IMPLEMENT["IMPLEMENT Mode<br>Rules"]
    Mode --> REFLECT["REFLECT Mode<br>Rules"]
    
    Level --> Level1["Level 1<br>Rules"]
    Level --> Level2["Level 2<br>Rules"]
    Level --> Level3["Level 3<br>Rules"]
    Level --> Level4["Level 4<br>Rules"]
```

## 📊 RULE LOADING PROTOCOL

```mermaid
sequenceDiagram
    participant User
    participant System
    participant RuleCache
    participant FileSystem
    
    User->>System: Request mode activation
    System->>System: (Internal: Check & Load Core, Common Rules)
    System->>System: (Internal: Load Essential Mode & Level Rules)
    System->>System: (Internal: Register lazy loaders for specialized rules)
    System->>User: Mode initialized
    
    User->>System: Request specialized functionality
    System->>RuleCache: Check specialized rule cache
    RuleCache-->>System: Return cached rule (if available)
    
    alt Rule not in cache
        System->>FileSystem: Load specialized rule
        FileSystem-->>System: Return specialized rule
        System->>RuleCache: Cache specialized rule
    end
    
    System->>User: Execute specialized functionality
```

## 📋 RULE DEPENDENCY MAP

This map shows which rules depend on others and are loaded as part of a hierarchy or for specific modes:

```mermaid
graph TD
    Main["main-optimized.mdc"] --> Core1["platform-awareness.mdc"]
    Main --> Core2["file-verification.mdc"]
    Main --> Core3["command-execution.mdc"]
    
    subgraph "VAN Mode"
        VanMap["van-mode-map.mdc"] --> Van1["van-complexity-determination.mdc"]
        VanMap --> Van2["van-platform-detection.mdc"]
    end
    
    subgraph "PLAN Mode"
        PlanMap["plan-mode-map.mdc"] --> Plan1["task-tracking-basic.mdc"]
        PlanMap --> Plan2["planning-comprehensive.mdc"]
    end
    
    subgraph "CREATIVE Mode"
        CreativeMap["creative-mode-map.mdc"] --> Creative1["creative-phase-enforcement.mdc"]
        CreativeMap --> Creative2["creative-phase-metrics.mdc"]
        Creative1 & Creative2 -.-> CreativeSpecialized["Specialized Creative Rules"]
        CreativeSpecialized --> CArch["creative-phase-architecture.mdc"]
        CreativeSpecialized --> CAlgo["creative-phase-algorithm.mdc"]
        CreativeSpecialized --> CUIUX["creative-phase-uiux.mdc"]
    end
    
    subgraph "IMPLEMENT Mode"
        ImplementMap["implement-mode-map.mdc"] --> Impl1["implementation-guide.mdc"]
        ImplementMap --> Impl2["testing-strategy.mdc"]
    end
```

## 🔍 MODE-SPECIFIC RULE LOADING (ESSENTIALS)

**Instructions:** When entering a mode, load these essential rules first. Specialized rules are loaded only on demand.

*   **VAN Mode:**
    *   `main-optimized.mdc` (Core)
    *   `Core/platform-awareness.mdc`
    *   `Core/file-verification.mdc`
    *   `visual-maps/van_mode_split/van-complexity-determination.mdc`
    *   `visual-maps/van_mode_split/van-platform-detection.mdc`
    *   (Optionally, `visual-maps/van-mode-map.mdc` if it consolidates other VAN sub-maps)

*   **PLAN Mode:**
    *   `main-optimized.mdc` (Core)
    *   `visual-maps/plan-mode-map.mdc`
    *   `LevelX/task-tracking-[complexity].mdc` (Loaded based on complexity)

*   **CREATIVE Mode:**
    *   `main-optimized.mdc` (Core)
    *   `visual-maps/creative-mode-map.mdc`
    *   `Core/creative-phase-enforcement.mdc`

*   **CREATIVE Mode Specialized Rules (Lazy Loaded - on demand):**
    *   `Phases/CreativePhase/creative-phase-architecture.mdc`
    *   (Add others like `creative-phase-algorithm.mdc`, `creative-phase-uiux.mdc` if they are created)

*   **IMPLEMENT Mode:**
    *   `main-optimized.mdc` (Core)
    *   `Core/command-execution.mdc`
    *   `visual-maps/implement-mode-map.mdc`

## 🚀 TOKEN EFFICIENCY BENEFITS

The hierarchical loading system provides:
1.  Reduced Initial Loading (only essentials).
2.  Cached Core Rules.
3.  Specialized Rule Loading (only when needed).
4.  Complexity-Based Loading.

## 🧪 RULE LOADING VERIFICATION

To verify the system is working:
*   Confirm Core, Mode-Essential, and Complexity-Level rules are loaded.
*   Confirm Specialized Rules are *not* loaded initially.
*   Monitor current token usage to ensure it aligns with expected savings.

```
✓ RULE LOADING VERIFICATION
- Core Rules: [Loaded/Not Loaded]
- Mode-Essential Rules: [Loaded/Not Loaded]
- Complexity-Level Rules: [Loaded/Not Loaded]
- Specialized Rules: [Loaded/Not Loaded] (Should be 'Not Loaded' initially)

Current Token Usage: [X] tokens
```
```

---

**/isolation_rules/Core/memory-bank-paths.mdc:**
```markdown
---
description: Defines canonical paths for core Memory Bank files.
globs: documentation\memory-bank-paths.mdc
alwaysApply: true
---

# CORE MEMORY BANK FILE LOCATIONS

**CRITICAL:** All core Memory Bank files reside within the `documentation\memory-bank/` directory at the project root. Do NOT create or modify these files outside this directory unless explicitly instructed for archiving purposes.

*   **Tasks File:** `documentation\memory-bank/tasks.md` - Used for active, in-progress task tracking. Its content, particularly detailed checklists, is merged into the main archive document upon completion. After archival, `tasks.md` is cleared. It is an ephemeral working document, with its persistent record captured in the task's archive file.
*   **Active Context File:** `documentation\memory-bank/activeContext.md`
*   **Progress File:** `documentation\memory-bank/progress.md`
*   **Project Brief File:** `documentation\memory-bank/projectbrief.md`
*   **Product Context File:** `documentation\memory-bank/productContext.md`
*   **System Patterns File:** `documentation\memory-bank/systemPatterns.md`
*   **Tech Context File:** `documentation\memory-bank/techContext.md`
*   **Style Guide File:** `documentation\memory-bank/style-guide.md`
*   **Creative Phase Docs:** `documentation\memory-bank/creative/creative-[feature_name].md`
*   **Reflection Docs:** `documentation\memory-bank/reflection/reflection-[task_id].md`
*   **Archive Directory:** `documentation\memory-bank/archive/archive-[task_id].md`

**Verification Mandate:** Before any `create_file` or `edit_file` operation on these core files, verify the path starts with `documentation\memory-bank/`. If attempting to create a new core file (e.g., `tasks.md` at the start of a project), ensure it is created at `documentation\memory-bank/tasks.md`.
```

---

**/isolation_rules/Core/mode-transition-optimization.mdc:**
```markdown
---
description: Optimized mode transition strategy for token efficiency.
globs: "**/transition*/**", "**/mode-switching*/**"
alwaysApply: false
---

# OPTIMIZED MODE TRANSITION

> **TL;DR:** This strategy ensures efficient mode transitions by minimizing token overhead and maximizing context preservation.

## 🔄 MODE TRANSITION WORKFLOW

```mermaid
sequenceDiagram
    participant CurrentMode
    participant ContextManager
    participant NextMode
    
    CurrentMode->>CurrentMode: Complete Phase Requirements
    CurrentMode->>ContextManager: Summarize & Store Critical Context
    ContextManager->>ContextManager: Optimize Context for Next Mode
    CurrentMode->>User: "Phase complete. NEXT MODE: [mode name]"
    User->>CurrentMode: End Current Mode
    User->>NextMode: Start Next Mode
    NextMode->>ContextManager: Request Relevant Context
    ContextManager-->>NextMode: Provide Optimized Context
    NextMode->>NextMode: Continue with Preserved Context
```

## 📋 CONTEXT TRANSFER PROTOCOL

When transitioning between modes, only the **critical, relevant context** for the *next* phase should be actively transferred.
**Instructions:**
1.  **Current Mode:** Before exiting, update `tasks.md` with the final status and key outcomes of the completed phase. Summarize critical information for `activeContext.md`.
2.  **Next Mode:** Upon activation, the new mode will:
    *   Read `tasks.md` for overall task status and next steps.
    *   Read `activeContext.md` for immediate focus.
    *   If specialized information is needed (e.g., design decisions in IMPLEMENT mode), load the relevant `creative-*.md` files *on demand*.

## 💡 TOKEN EFFICIENCY IN TRANSITIONS

-   **Avoid Full Context Duplication:** Do not copy the *entire* previous mode's working memory.
-   **Leverage Memory Bank Files:** `tasks.md`, `activeContext.md`, `progress.md` serve as the primary persistent context.
-   **Lazy Loading of Detailed Rules:** Only load `creative-*.md` or other detailed rules when explicitly required by the next mode's logic, not upon general mode entry.
-   **Summarization:** Encourage concise summaries in `activeContext.md` or `progress.md` for quick overview rather than full detail copy-pasting.

## 📌 TRANSITION MESSAGES

Use these messages to guide the user during transitions:

### Phase Completion & Next Mode Prompt:
```
✅ [Current Phase] Complete
➡️ NEXT RECOMMENDED MODE: [Next Mode Name]

Type '[Next Mode Name]' to proceed.
```

### Context Preservation Confirmation (after new mode activates):
```
Continuing from previous work.
Current task focus: [Summary from activeContext.md]
Task status: [Status from tasks.md]
```

## 🚨 TRANSITION BLOCKERS

If the `tasks.md` or `activeContext.md` are not in the expected state for the next mode, provide clear instructions:

```
⛔️ MODE TRANSITION BLOCKED
Reason: [Explanation, e.g., "Tasks for current phase not marked complete in tasks.md"]
Action: Please return to [Previous Mode] and complete necessary steps.
```
```

---

**/isolation_rules/Core/optimization-integration.mdc:**
```markdown
---
description: Integration hub for Memory Bank optimizations
globs: "**/optimization*/**", "**/integration*/**"
alwaysApply: false
---

# MEMORY BANK OPTIMIZATION INTEGRATION

> **TL;DR:** This file serves as the integration point for all Memory Bank optimizations, coordinating the various optimization components to work seamlessly together.

## 🔄 OPTIMIZATION INTEGRATION FLOW

```mermaid
graph TD
    Start["Memory Bank<br>Initialization"] --> HRL["Hierarchical<br>Rule Loading"]
    HRL --> ACM["Adaptive<br>Complexity Model"]
    ACM --> DCM["Dynamic<br>Context Management"]
    DCM --> TMO["Transition<br>Optimization"]
    
    subgraph "Level-Specific Optimizations"
        L1["Level 1<br>Optimizations"]
        L2["Level 2<br>Optimizations"]
        L3["Level 3<br>Optimizations"]
        L4["Level 4<br>Optimizations"]
    end
    
    ACM --> L1 & L2 & L3 & L4
    
    L1 & L2 & L3 & L4 --> CPO["Creative Phase<br>Optimization"]
    
    CPO --> PDO["Progressive<br>Documentation"]
    TMO --> PDO
    
    PDO --> MBO["Memory Bank<br>Optimization"]
```

## 🔄 OPTIMIZATION INITIALIZATION SEQUENCE

**Instructions:** Initialize optimizations in the following priority order, ensuring dependencies are met.

```mermaid
sequenceDiagram
    participant MB as Memory Bank
    participant HRL as Hierarchical Rule Loading
    participant ACM as Adaptive Complexity
    participant TMO as Transition Optimization
    participant CPO as Creative Phase Optimization
    
    MB->>HRL: Initialize (Priority 1)
    HRL-->>MB: Initialization complete
    MB->>ACM: Initialize (Priority 2)
    ACM->>HRL: (Requests rule loading services)
    ACM-->>MB: Initialization complete
    MB->>TMO: Initialize (Priority 3)
    TMO->>HRL: (Requests rule loading services)
    TMO->>ACM: (Requests complexity model)
    TMO-->>MB: Initialization complete
    MB->>CPO: Initialize (Final)
    CPO->>HRL: (Requests rule loading services)
    CPO->>ACM: (Requests complexity model)
    CPO->>TMO: (Requests transition services)
    CPO-->>MB: Initialization complete
    MB->>MB: All optimizations initialized
```

## 🔍 OPTIMIZATION CONFIGURATION

**Instructions:** Configure the following parameters to control optimization behavior.

*   **Token Optimization:**
    *   `enableHierarchicalLoading`: `true` (Always enable)
    *   `enableProgressiveDocumentation`: `true` (Always enable)
    *   `enableLazyRuleLoading`: `true` (Always enable)
    *   `enableContextPruning`: `true` (Always enable)
*   **Context Preservation:**
    *   `contextCompressionLevel`: `high` (minimal relevant context transferred)
*   **Documentation Optimization:**
    *   `level1DocumentationLevel`: `minimal`
    *   `level2DocumentationLevel`: `standard`
    *   `level3DocumentationLevel`: `comprehensive`
    *   `level4DocumentationLevel`: `comprehensive`
    *   `enableProgressiveDisclosure`: `true` (for templates)
    *   `enableTemplateCaching`: `true` (for frequent templates)

## 📊 OPTIMIZATION MONITORING

```mermaid
graph TD
    Monitor["Optimization<br>Monitor"] --> TokenUsage["Token Usage<br>Tracking"]
    Monitor --> ContextEfficiency["Context<br>Efficiency"]
    Monitor --> RuleLoadingStats["Rule Loading<br>Statistics"]
    Monitor --> DocumentationSize["Documentation<br>Size"]
    
    TokenUsage & ContextEfficiency & RuleLoadingStats & DocumentationSize --> Dashboard["Optimization<br>Dashboard"]
    
    Dashboard --> Feedback["Optimization<br>Feedback Loop"]
    Feedback --> Config["Optimization<br>Configuration"]
    Config --> Monitor
```

## 📈 OPTIMIZATION METRICS

```markdown
# Optimization Metrics

## Token Usage
- Core Rule Loading: [X] tokens
- Mode-Specific Rules: [Y] tokens (cumulative, if loaded)
- Creative Phase Documentation: [Z] tokens (per document)
- Overall Token Reduction: [P]% (compared to non-optimized baseline)

## Context Efficiency
- Context Utilization: [Q]% (relevant context vs. total input)
- Context Waste: [R]% (irrelevant context)
- Effective Token Capacity: [S] tokens (available for current task)

## Rule Loading
- Rules Loaded: [T] / [U] (Total available)
- Lazy-Loaded Rules: [V] (number of times lazy loaded)
- Cached Rules: [W] (number of rules in cache)

## Documentation
- Level 1 Documentation Size: [X] tokens
- Level 2 Documentation Size: [Y] tokens
- Level 3 Documentation Size: [Z] tokens
- Level 4 Documentation Size: [AA] tokens
```

## 🔄 INTEGRATION USAGE EXAMPLES

### Initializing All Optimizations
**Instructions:** At system startup, ensure all optimization rules are loaded and their configurations applied. This is implicitly managed by the `main-optimized.mdc` entry point.

### Using Optimized Creative Phase
**Instructions:** Follow the `optimized-creative-template.mdc` when generating design decisions. Start with the compact template and expand sections (like detailed analysis) only when prompted or necessary.

### Mode Transition Example
**Instructions:** When a phase is complete and a mode transition is triggered, ensure `tasks.md` is updated and context is summarized for the next mode as per `mode-transition-optimization.mdc`.

### Hierarchical Rule Loading Example
**Instructions:** The system automatically manages this. When a specialized function is required (e.g., in CREATIVE mode, architecture design is needed), the relevant rule (`creative-phase-architecture.mdc`) will be loaded *only then*.

These integrated optimizations work seamlessly together to provide a significantly more efficient Memory Bank system while maintaining all functionality.
```

---

**/isolation_rules/Core/platform-awareness.mdc:**
```markdown
---
description: Platform detection and command adaptation for isolation-focused Memory Bank
globs: platform-awareness.mdc
alwaysApply: false
---


# PLATFORM AWARENESS SYSTEM

> **TL;DR:** This system detects the operating system, path format, and shell environment, then adapts commands accordingly to ensure cross-platform compatibility.

## 🔍 PLATFORM DETECTION PROCESS

```mermaid
graph TD
    Start["Start Platform<br>Detection"] --> DetectOS["Detect OS<br>Environment"]
    DetectOS --> Windows["Windows<br>Detection"]
    DetectOS --> Mac["macOS<br>Detection"]
    DetectOS --> Linux["Linux<br>Detection"]
    
    Windows & Mac & Linux --> PathCheck["Path Separator<br>Detection"]
    PathCheck --> CmdAdapt["Command<br>Adaptation"]
    CmdAdapt --> ShellCheck["Shell Type<br>Detection"]
    ShellCheck --> Complete["Platform Detection<br>Complete"]
```

## 📋 PLATFORM DETECTION IMPLEMENTATION

**Instructions:** Determine the current operating system, path separator, and shell environment.

```
## Platform Detection Results
Operating System: [Windows/macOS/Linux]
Path Separator: [\ or /]
Shell Environment: [PowerShell/Bash/Zsh/Cmd]
Command Adaptation: [Required/Not Required]

Adapting commands for [detected platform]...
```

## 🔍 PATH FORMAT CONVERSION

**Instructions:** When generating paths for commands or file operations, use the detected path separator.

```mermaid
sequenceDiagram
    participant Input as Path Input
    participant Detector as Format Detector
    participant Converter as Format Converter
    participant Output as Adapted Path
    
    Input->>Detector: Raw Path
    Detector->>Detector: Detect Current Format
    Detector->>Converter: Path + Current Format
    Converter->>Converter: Apply Target Format
    Converter->>Output: Platform-Specific Path
```

## 📝 PLATFORM VERIFICATION CHECKLIST

```
✓ PLATFORM VERIFICATION
- Operating system correctly identified? [YES/NO]
- Path separator format detected? [YES/NO]
- Shell environment identified? [YES/NO]
- Command set adapted appropriately? [YES/NO]
- Path format handling configured? [YES/NO]

→ If all YES: Platform adaptation complete
→ If any NO: Run additional detection steps
```
```

---

**/isolation_rules/Level1/optimized-workflow-level1.mdc:**
```markdown
---
description: Optimized Level 1 workflow for quick bug fixes with token efficiency
globs: "**/level1*/**", "**/quick*/**", "**/bugfix*/**"
alwaysApply: false
---

# OPTIMIZED LEVEL 1 WORKFLOW

> **TL;DR:** This streamlined workflow for Level 1 tasks (quick bug fixes) optimizes for speed and token efficiency while maintaining quality.

## 🔧 LEVEL 1 PROCESS FLOW

```mermaid
graph TD
    Start["START LEVEL 1<br>QUICK FIX"] --> Analyze["1️⃣ ANALYZE<br>Understand issue"]
    Analyze --> Implement["2️⃣ IMPLEMENT<br>Fix the issue"]
    Implement --> Verify["3️⃣ VERIFY<br>Test the fix"]
    Verify --> Document["4️⃣ DOCUMENT<br>Record solution"]

```

## 📝 CONSOLIDATED DOCUMENTATION

Level 1 tasks use a single-file approach to minimize context switching:

```markdown
# QUICK FIX: [Issue Name]

## Issue Summary
- Type: [Bug/Hotfix/Quick Enhancement]
- Priority: [Low/Medium/High/Critical]
- Reported by: [Name/System]
- Affected area: [Component/Feature]

## Analysis
- Root cause: [Brief description]
- Affected files: [List of files]
- Impact: [Scope of impact]

## Solution
- Approach: [Brief description]
- Changes made: [List of changes]
- Commands executed: [Key commands]

## Verification
- Testing: [How the fix was tested]
- Results: [Test results]
- Additional checks: [Any other verification]

## Status
- [x] Fix implemented
- [x] Tests passed
- [x] Documentation updated
```

## 🔄 MEMORY BANK UPDATE

Level 1 tasks use a simplified Memory Bank update with minimal overhead:

```markdown
## tasks.md Update (Level 1)

### Task: [Task Name]
- Status: Complete
- Implementation: [One-line summary]
- Link to fix: [File/line reference]
```

## ⚡ TOKEN-OPTIMIZED TEMPLATE

For maximum efficiency, Level 1 tasks can use this ultra-compact template:

```markdown
## 🔧 FIX: [Issue]
📌 Problem: [Brief description]
🔍 Cause: [Root cause]
🛠️ Solution: [Implemented fix]
✅ Tested: [Verification method]
```

## 📊 QUICK TEMPLATES FOR COMMON ISSUES

### Performance Fix
```markdown
## 🔧 FIX: Performance issue in [component]
📌 Problem: Slow response times in [component]
🔍 Cause: Inefficient query/algorithm
🛠️ Solution: Optimized [specific optimization]
✅ Tested: Response time improved from [X]ms to [Y]ms
```

### Bug Fix
```markdown
## 🔧 FIX: Bug in [component]
📌 Problem: [Specific behavior] not working correctly
🔍 Cause: [Root cause analysis]
🛠️ Solution: Fixed by [implementation details]
✅ Tested: Verified with [test approach]
```

### Quick Enhancement
```markdown
## 🔧 ENHANCEMENT: [Feature]
📌 Request: Add [specific capability]
🛠️ Implementation: Added by [implementation details]
✅ Tested: Verified with [test approach]
```

## ✅ STREAMLINED VERIFICATION

Level 1 tasks use a minimal verification process:

```markdown
VERIFICATION:
[x] Fix implemented and tested
[x] No regressions introduced
[x] Documentation updated
```

## 🚀 CONSOLIDATED MEMORY BANK UPDATE

Optimize Memory Bank updates for Level 1 tasks by using a single operation.
**Instructions:** Update `tasks.md` by appending the completion status and `activeContext.md` / `progress.md` with a brief one-line summary if relevant.

## 🔄 OPTIMIZED LEVEL 1 WORKFLOW EXAMPLE

```markdown
## 🔧 FIX: Login button not working on mobile devices

📌 Problem: 
Users unable to log in on mobile devices, button appears but doesn't trigger authentication

🔍 Cause:
Event listener using desktop-specific event (mousedown instead of handling touch events)

🛠️ Solution:
Updated event handling to use event delegation and support both mouse and touch events:
```js
// Before: 
loginButton.addEventListener('mousedown', handleLogin);

// After:
loginButton.addEventListener('mousedown', handleLogin);
loginButton.addEventListener('touchstart', handleLogin);
```

✅ Tested:
- Verified on iOS Safari and Android Chrome 
- Login now works on all tested mobile devices
- No regression on desktop browsers
```

## ⚡ TOKEN EFFICIENCY BENEFITS

This optimized Level 1 workflow provides:

1.  Reduced documentation overhead.
2.  Consolidated Memory Bank updates.
3.  Focused verification process.
4.  Template-based approach for common scenarios.
5.  Streamlined workflow with fewer steps.

The updated approach maintains all critical information while significantly reducing token usage.
```

---

**/isolation_rules/Level2/archive-basic.mdc:**
```markdown
---
description: Basic archiving approach for Level 2 Simple Enhancement tasks
globs: "**/level2/**", "**/archive/**", "**/completion/**"
alwaysApply: false
---

# BASIC ARCHIVING FOR LEVEL 2 TASKS

> **TL;DR:** This document outlines a basic archiving approach for Level 2 (Simple Enhancement) tasks, ensuring that completed work is properly documented and knowledge is preserved with minimal overhead.

## 🔍 ARCHIVING OVERVIEW

Even for Level 2 tasks, proper archiving ensures that completed work is documented and knowledge is preserved. This basic archiving approach provides sufficient structure while maintaining efficiency.

## 📋 ARCHIVING PRINCIPLES

1.  **Completion**: Clearly document what was completed
2.  **Context**: Preserve the context of the enhancement
3.  **Knowledge**: Capture key insights and lessons
4.  **Findability**: Make archived information easy to find
5.  **References**: Create cross-references to related work

## 📋 BASIC ARCHIVE STRUCTURE

```markdown
# Enhancement Archive: [Feature Name]

## Summary
[Brief summary of the enhancement]

## Date Completed
YYYY-MM-DD

## Key Files Modified
- [File path 1]
- [File path 2]
- [File path 3]

## Requirements Addressed
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

## Implementation Details
[Brief description of how the enhancement was implemented]

## Testing Performed
- [Test 1]
- [Test 2]
- [Test 3]

## Lessons Learned
- [Lesson 1]
- [Lesson 2]
- [Lesson 3]

## Related Work
- [Link to related task/enhancement 1]
- [Link to related task/enhancement 2]

## Notes
[Any additional information or context]
```

## 📋 ARCHIVE LOCATION

Store archives in an organized structure:

```
docs/
└── archive/
    └── enhancements/
        └── YYYY-MM/
            ├── feature-name-1.md
            └── feature-name-2.md
```

## 📋 ARCHIVING PROCESS

Follow these steps to archive a Level 2 task:

1.  **Prepare Archive Content**:
    - Gather all relevant information
    - Fill in the archive template
    - Include all key implementation details

2.  **Cross-Reference Creation**:
    - Update tasks.md with link to archive
    - Add reference in progress.md
    - Update activeContext.md with next focus

3.  **File Creation and Storage**:
    - Create appropriate directory if needed (e.g., `docs/archive/enhancements/YYYY-MM/`)
    - Save archive file with descriptive name (e.g., `feature-name-YYYYMMDD.md`)
    - Ensure file follows naming convention

4.  **Final Verification**:
    - Check archive for completeness
    - Verify all cross-references
    - Ensure all links are working

## 📋 CROSS-REFERENCE FORMAT

When creating cross-references:

1.  **In tasks.md**:
    ```markdown
    ## Completed Enhancements
    - [X] [Feature Name] (YYYY-MM-DD) - [Archive Link](../docs/archive/enhancements/YYYY-MM/feature-name.md)
    ```

2.  **In progress.md**:
    ```markdown
    ## Completed Milestones
    - [Feature Name] enhancement completed on YYYY-MM-DD. See [archive entry](../docs/archive/enhancements/YYYY-MM/feature-name.md).
    ```

3.  **In activeContext.md**:
    ```markdown
    ## Recently Completed
    - [Feature Name] enhancement is now complete. Archive: [link](../docs/archive/enhancements/YYYY-MM/feature-name.md)
    
    ## Current Focus
    - Moving to [Next Task Name]
    ```

## 📋 ARCHIVING VERIFICATION CHECKLIST

```
✓ ARCHIVE VERIFICATION
- Archive content complete? [YES/NO]
- Archive properly stored? [YES/NO]
- Cross-references created? [YES/NO]
- tasks.md updated? [YES/NO]
- progress.md updated? [YES/NO]
- activeContext.md updated? [YES/NO]

→ If all YES: Archiving complete
→ If any NO: Complete archiving process
```

## 📋 MINIMAL MODE ARCHIVING

For minimal mode, use this format:

```
✓ ARCHIVE: [Feature Name]
✓ DATE: YYYY-MM-DD
✓ FILES: [Key files changed]
✓ SUMMARY: [One-sentence summary]
✓ LESSONS: [Key takeaway]
✓ REFS: [tasks.md, progress.md, activeContext.md]
```

## 🚨 KNOWLEDGE PRESERVATION PRINCIPLE

Remember:

```
┌─────────────────────────────────────────────────────┐
│ Archive files are a VALUABLE KNOWLEDGE RESOURCE.    │
│ Take care to preserve insights and lessons that     │
│ will benefit future work.                           │
└─────────────────────────────────────────────────────┘
```
```

---

**/isolation_rules/Level2/reflection-basic.mdc:**
```markdown
---
description: Basic reflection format for Level 2 Simple Enhancement tasks
globs: "**/level2/**", "**/reflection/**"
alwaysApply: false
---

# BASIC REFLECTION FOR LEVEL 2 TASKS

> **TL;DR:** This document outlines a basic reflection approach for Level 2 (Simple Enhancement) tasks, ensuring that key insights and lessons are captured without unnecessary overhead.

## 🔍 REFLECTION OVERVIEW

Reflection is essential for improving future work, even for simpler Level 2 enhancements. This basic reflection approach focuses on key outcomes, challenges, and lessons learned while maintaining efficiency.

## 📋 REFLECTION PRINCIPLES

1.  **Honesty**: Accurately represent successes and challenges
2.  **Specificity**: Include concrete examples and observations
3.  **Insight**: Go beyond surface observations to derive useful insights
4.  **Improvement**: Focus on actionable takeaways for future work
5.  **Efficiency**: Keep reflection concise and focused on key learnings

## 📋 BASIC REFLECTION STRUCTURE

```markdown
# Level 2 Enhancement Reflection: [Feature Name]

## Enhancement Summary
[Brief one-paragraph summary of the enhancement]

## What Went Well
- [Specific success point 1]
- [Specific success point 2]
- [Specific success point 3]

## Challenges Encountered
- [Specific challenge 1]
- [Specific challenge 2]
- [Specific challenge 3]

## Solutions Applied
- [Solution to challenge 1]
- [Solution to challenge 2]
- [Solution to challenge 3]

## Key Technical Insights
- [Technical insight 1]
- [Technical insight 2]
- [Technical insight 3]

## Process Insights
- [Process insight 1]
- [Process insight 2]
- [Process insight 3]

## Action Items for Future Work
- [Specific action item 1]
- [Specific action item 2]
- [Specific action item 3]

## Time Estimation Accuracy
- Estimated time: [X hours/days]
- Actual time: [Y hours/days]
- Variance: [Z%]
- Reason for variance: [Brief explanation]
```

## 📋 REFLECTION QUALITY

High-quality reflections for Level 2 tasks should:

1.  **Provide specific examples** rather than vague statements
2.  **Identify concrete takeaways** not general observations
3.  **Connect challenges to solutions** with clear reasoning
4.  **Analyze estimation accuracy** to improve future planning
5.  **Generate actionable improvements** for future work

## 📋 REFLECTION PROCESS

Follow these steps for effective Level 2 task reflection:

1.  **Schedule Reflection**:
    - Allocate dedicated time for reflection
    - Complete reflection within 24 hours of task completion

2.  **Gather Information**:
    - Review the original task requirements
    - Examine implementation details
    - Consider challenges encountered
    - Review time tracking data

3.  **Complete Template**:
    - Fill in all sections of the reflection template
    - Include specific, concrete examples
    - Be honest about challenges

4.  **Extract Insights**:
    - Identify patterns in challenges
    - Connect challenges to potential future improvements
    - Consider process improvements

5.  **Document Action Items**:
    - Create specific, actionable improvements
    - Link these to future tasks where applicable

6.  **Store Reflection**:
    - Save reflection with the task archive (or as `documentation/memory-bank/reflection/reflection-[task_id].md`)
    - Add cross-references to relevant documents

## 📋 EXAMPLES: VAGUE VS. SPECIFIC ENTRIES

### ❌ Vague Entries (Insufficient)

- "The implementation went well."
- "We had some challenges with the code."
- "The feature works as expected."

### ✅ Specific Entries (Sufficient)

- "The modular approach allowed for easy integration with the existing codebase, specifically the clean separation between the UI layer and data processing logic."
- "Challenge: The state management became complex when handling multiple user interactions. Solution: Implemented a more structured reducer pattern with clear actions and state transitions."
- "Action Item: Create a reusable component for file selection that handles all the edge cases we encountered in this implementation."

## 📋 REFLECTION VERIFICATION CHECKLIST

```
✓ REFLECTION VERIFICATION
- All template sections completed? [YES/NO]
- Specific examples provided? [YES/NO]
- Challenges honestly addressed? [YES/NO]
- Concrete solutions documented? [YES/NO]
- Actionable insights generated? [YES/NO]
- Time estimation analyzed? [YES/NO]

→ If all YES: Reflection complete
→ If any NO: Improve reflection quality
```

## 📋 MINIMAL MODE REFLECTION

For minimal mode, use this format:

```
✓ REFLECTION: [Feature Name]
✓ WENT WELL: [Key success]
✓ CHALLENGE: [Key challenge]
✓ SOLUTION: [Key solution]
✓ INSIGHT: [Most important takeaway]
✓ ACTION: [Top priority action item]
✓ TIME: Est [X] vs. Actual [Y] ([Z%] variance)
```

## 🚨 CONTINUOUS IMPROVEMENT PRINCIPLE

Remember:

```
┌─────────────────────────────────────────────────────┐
│ Every reflection should produce at least ONE        │
│ actionable improvement for future work.             │
└─────────────────────────────────────────────────────┘
```
```

---

**/isolation_rules/Level2/task-tracking-basic.mdc:**
```markdown
---
description: Basic task tracking for Level 2 Simple Enhancement tasks
globs: "**/level2/**", "**/tracking/**", "**/task/**"
alwaysApply: false
---

# BASIC TASK TRACKING FOR LEVEL 2

> **TL;DR:** This document outlines a streamlined task tracking approach for Level 2 (Simple Enhancement) tasks. It provides a balanced framework for managing task progress with minimal overhead.

## 🔍 TASK TRACKING OVERVIEW

Level 2 tasks require a more structured tracking approach than Level 1, but don't need the comprehensive tracking of higher-level tasks. This basic tracking system provides sufficient structure while maintaining efficiency.

## 📋 TASK TRACKING PRINCIPLES

1.  **Clarity**: Tasks should be clearly defined
2.  **Visibility**: Progress should be visible at a glance
3.  **Structure**: Break work into logical subtasks
4.  **Updates**: Keep progress regularly updated
5.  **Completion**: Clearly mark when tasks are done

## 📋 TASK STRUCTURE FOR LEVEL 2

```markdown
## [Feature Name] Enhancement

**Status**: [Not Started/In Progress/Complete]
**Priority**: [High/Medium/Low]
**Estimated Effort**: [Small/Medium/Large]

### Description
[Brief description of the enhancement]

### Requirements
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

### Subtasks
- [ ] [Subtask 1]
- [ ] [Subtask 2]
- [ ] [Subtask 3]

### Dependencies
- [Dependency 1]
- [Dependency 2]

### Notes
[Any additional information or context]
```

## 📋 TASKS.MD ORGANIZATION

Organize tasks.md with these sections for Level 2 tasks:

```markdown
# Tasks

## Active Enhancements
- [Enhancement 1] - [Status]
- [Enhancement 2] - [Status]

## Enhancement Details
### [Enhancement 1]
[Task structure as above]

### [Enhancement 2]
[Task structure as above]

## Completed Enhancements
- [X] [Completed Enhancement 1] (YYYY-MM-DD)
- [X] [Completed Enhancement 2] (YYYY-MM-DD)
```

## 📋 UPDATING TASK STATUS

Update tasks using this process:

1.  **Starting a Task**:
    - Update Status to "In Progress"
    - Add start date to Notes

2.  **Progress Updates**:
    - Check off subtasks as completed
    - Add brief notes about progress
    - Update any changed requirements

3.  **Completing a Task**:
    - Update Status to "Complete"
    - Check off all subtasks
    - Move to Completed Enhancements
    - Add completion date

## 📋 SUBTASK MANAGEMENT

For Level 2 tasks, subtasks should:

1.  Be actionable and specific
2.  Represent approximately 30-60 minutes of work
3.  Follow a logical sequence
4.  Be updated as soon as completed
5.  Include verification steps

Example of well-structured subtasks:
```markdown
### Subtasks
- [ ] Review existing implementation of related features
- [ ] Create draft UI design for new button
- [ ] Add HTML structure for new component
- [ ] Implement button functionality in JavaScript
- [ ] Add appropriate styling in CSS
- [ ] Add event handling
- [ ] Test on desktop browsers
- [ ] Test on mobile browsers
- [ ] Update user documentation
```

## 📋 PROGRESS VISUALIZATION

Use progress indicators to show status:

```markdown
### Progress
[###-------] 30% Complete
```

For subtasks:
```markdown
### Subtasks (3/10 Complete)
- [X] Subtask 1
- [X] Subtask 2
- [X] Subtask 3
- [ ] Subtask 4
- [ ] Subtask 5
```

## 📋 TRACKING VERIFICATION CHECKLIST

```
✓ TASK TRACKING VERIFICATION
- Task clearly defined? [YES/NO]
- Requirements listed? [YES/NO]
- Subtasks created? [YES/NO]
- Dependencies identified? [YES/NO]
- Status up-to-date? [YES/NO]

→ If all YES: Task tracking is adequate
→ If any NO: Update task tracking
```

## 📋 MINIMAL MODE TRACKING

For minimal mode, use this format:

```
✓ TASK: [Enhancement name]
✓ STATUS: [In Progress/Complete]
✓ SUBTASKS: [X/Y Complete]
✓ NEXT: [Next action]
```

## 🚨 TASKS.MD PRIMACY PRINCIPLE

Remember:

```
┌─────────────────────────────────────────────────────┐
│ tasks.md is the SINGLE SOURCE OF TRUTH for ALL      │
│ task tracking. ALL task updates MUST be reflected   │
│ in tasks.md IMMEDIATELY.                            │
└─────────────────────────────────────────────────────┘
```
```

---

**/isolation_rules/Level2/workflow-level2.mdc:**
```markdown
---
description: Basic workflow for Level 2 Simple Enhancement tasks
globs: "**/level2/**", "**/workflow/**"
alwaysApply: false
---
# WORKFLOW FOR LEVEL 2 TASKS

> **TL;DR:** This document outlines a structured yet efficient workflow for Level 2 (Simple Enhancement) tasks, including 6 key phases with milestone checkpoints and quality verification.

## 🔍 LEVEL 2 WORKFLOW OVERVIEW

```mermaid
graph LR
    Init["1. INITIALIZATION"] --> Doc["2. DOCUMENTATION<br>SETUP"]
    Doc --> Plan["3. TASK<br>PLANNING"]
    Plan --> Impl["4. IMPLEMENTATION"]
    Impl --> Reflect["5. REFLECTION"]
    Reflect --> Archive["6. ARCHIVING"]
    
    %% Document connections for each phase
    Init -.-> InitDocs["Quick setup<br>Issue understanding"]
    Doc -.-> DocDocs["Memory bank update<br>Templates"]
    Plan -.-> PlanDocs["Requirements<br>Subtasks<br>Estimates"]
    Impl -.-> ImplDocs["Code changes<br>Status updates<br>Verification"]
    Reflect -.-> ReflectDocs["Successes<br>Challenges<br>Lessons"]
    Archive -.-> ArchiveDocs["Consolidate<br>Link<br>Finalize"]
```

## 📋 WORKFLOW PHASES

### Phase 1: INITIALIZATION

**Steps:**
1.  Platform detection (use `Core/platform-awareness.mdc`).
2.  Critical file verification (use `Core/file-verification.mdc`).
3.  Memory Bank structure loading (handled by Core rules).
4.  Task creation in `tasks.md`.
5.  Initial task scope definition.

**Milestone Checkpoint:**
```
✓ INITIALIZATION CHECKPOINT
- Platform detected and configured? [YES/NO]
- Critical files verified? [YES/NO]
- Task created in tasks.md? [YES/NO]
- Initial scope defined? [YES/NO]

→ If all YES: Proceed to Documentation Setup
→ If any NO: Complete initialization steps
```

### Phase 2: DOCUMENTATION SETUP

**Steps:**
1.  Load basic documentation templates.
2.  Update `projectbrief.md` with enhancement details.
3.  Update `activeContext.md` with current focus.
4.  Create minimal documentation structure (if not handled by templates).

**Milestone Checkpoint:**
```
✓ DOCUMENTATION CHECKPOINT
- Documentation templates loaded? [YES/NO]
- projectbrief.md updated? [YES/NO]
- activeContext.md updated? [YES/NO]
- Documentation structure created? [YES/NO]

→ If all YES: Proceed to Task Planning
→ If any NO: Complete documentation setup
```

### Phase 3: TASK PLANNING

**Steps:**
1.  Define clear requirements.
2.  Break down into subtasks.
3.  Update `tasks.md` with subtasks.
4.  Create time estimates.
5.  Document dependencies and constraints.

**Milestone Checkpoint:**
```
✓ PLANNING CHECKPOINT
- Requirements clearly defined? [YES/NO]
- Task broken down into subtasks? [YES/NO]
- tasks.md updated with subtasks? [YES/NO]
- Time estimates created? [YES/NO]
- Dependencies documented? [YES/NO]

→ If all YES: Proceed to Implementation
→ If any NO: Complete planning steps
```

### Phase 4: IMPLEMENTATION

**Steps:**
1.  Implement subtasks iteratively.
2.  Update status in `tasks.md` after each subtask.
3.  Perform basic verification of complete implementation.

**Milestone Checkpoint:**
```
✓ IMPLEMENTATION CHECKPOINT
- All subtasks completed? [YES/NO]
- Status updates maintained? [YES/NO]
- Enhancement fully implemented? [YES/NO]
- Basic verification performed? [YES/NO]
- tasks.md fully updated? [YES/NO]

→ If all YES: Proceed to Reflection
→ If any NO: Complete implementation steps
```

### Phase 5: REFLECTION

**Steps:**
1.  Load reflection template (`Level2/reflection-basic.mdc`).
2.  Review completed enhancement.
3.  Document successes and challenges.
4.  Extract key insights.
5.  Define action items for future work.

**Milestone Checkpoint:**
```
✓ REFLECTION CHECKPOINT
- Reflection template loaded? [YES/NO]
- Enhancement reviewed? [YES/NO]
- Successes and challenges documented? [YES/NO]
- Key insights extracted? [YES/NO]
- Action items defined? [YES/NO]

→ If all YES: Proceed to Archiving
→ If any NO: Complete reflection steps
```

### Phase 6: ARCHIVING

**Steps:**
1.  Load archive template (`Level2/archive-basic.mdc`).
2.  Gather implementation details.
3.  Create archive document.
4.  Create cross-references.
5.  Update Memory Bank files (`tasks.md`, `progress.md`, `activeContext.md`).

**Milestone Checkpoint:**
```
✓ ARCHIVING CHECKPOINT
- Archive template loaded? [YES/NO]
- Implementation details gathered? [YES/NO]
- Archive document created? [YES/NO]
- Cross-references created? [YES/NO]
- Memory Bank files updated? [YES/NO]

→ If all YES: Task Complete
→ If any NO: Complete archiving steps
```

## 📋 WORKFLOW VERIFICATION CHECKLIST

```
✓ FINAL WORKFLOW VERIFICATION
- All phases completed? [YES/NO]
- All milestone checkpoints passed? [YES/NO]
- tasks.md fully updated? [YES/NO]
- Reflection document created? [YES/NO]
- Archive document created? [YES/NO]
- Memory Bank fully updated? [YES/NO]

→ If all YES: Level 2 Task Successfully Completed
→ If any NO: Address outstanding items
```

## 📋 MINIMAL MODE WORKFLOW

For minimal mode, use this streamlined workflow:

```
1. INIT: Verify environment, create task entry
2. DOCS: Update projectbrief and activeContext
3. PLAN: Define requirements, subtasks, estimates
4. IMPL: Complete subtasks, update status
5. REFLECT: Document key insights and actions
6. ARCHIVE: Document completion and cross-reference
```

## 🔄 LEVEL TRANSITION HANDLING

```mermaid
graph TD
    L2["Level 2 Task"] --> Assess["Continuous<br>Assessment"]
    
    Assess --> Down["Downgrade to<br>Level 1"]
    Assess --> Up["Upgrade to<br>Level 3/4"]
    
    Down --> L1Trigger["Triggers:<br>- Simpler than expected<br>- Quick fix possible<br>- Single component"]
    
    Up --> L34Trigger["Triggers:<br>- More complex<br>- Multiple components<br>- Design needed"]
    
    L1Trigger --> L1Switch["Switch to<br>Level 1 Workflow"]
    L34Trigger --> L34Switch["Switch to<br>Level 3/4 Workflow"]
```

## 🚨 EFFICIENCY PRINCIPLE

Remember:

```
┌─────────────────────────────────────────────────────┐
│ Level 2 workflow balances PROCESS with EFFICIENCY.  │
│ Follow the structure but avoid unnecessary overhead. │
└─────────────────────────────────────────────────────┘
```
```

---

**/isolation_rules/Level3/archive-intermediate.mdc:**
```markdown
---
description: Archive process for Level 3 intermediate features.
globs: archive-intermediate.mdc
alwaysApply: false
---

# LEVEL 3 ARCHIVE: INTERMEDIATE FEATURE DOCUMENTATION

> **TL;DR:** This guide outlines the archiving process for a completed Level 3 intermediate feature. The aim is to create a self-contained, easily accessible record of the feature's development lifecycle, including its planning, design decisions, implementation summary, and reflection.

## 🚀 Before You Start Archiving (L3 Pre-Archive Checklist)

1.  **Confirm Reflection Complete:** Verify in `documentation\memory-bank/tasks.md` that the reflection phase for this feature is marked as complete and `documentation\memory-bank/reflection-[feature_id].md` exists and is finalized.
2.  **Gather All Feature-Specific Documents:**
    *   The feature plan section from `documentation\memory-bank/tasks.md` (or a copy of it).
    *   All `documentation\memory-bank/creative/creative-[aspect_name].md` documents related to this feature.
    *   The `documentation\memory-bank/reflection/reflection-[feature_id].md` document.
    *   Key diagrams or architectural notes from `documentation\memory-bank/progress.md` if not captured elsewhere.
    *   A link to the primary commit(s) or feature branch merge for the implemented code.

## 📦 Level 3 Archiving Workflow

```mermaid
graph TD
    StartArchive["Start L3 Archiving"] -->
    VerifyReflect["1. Verify Reflection Complete<br>Check `tasks.md` & `reflection-[feature_id].md`"] -->
    GatherDocs["2. Gather All Feature Documents<br>(Plan, Creative outputs, Reflection, Code links)"] -->
    CreateArchiveFile["3. Create Feature Archive File<br>e.g., `documentation\memory-bank/archive/feature-[FeatureNameOrID]_YYYYMMDD.md`"] -->
    PopulateArchive["4. Populate Archive File<br>(Using L3 Archive Template below)"] -->
    VerifyLinks["5. Verify All Internal Links<br>in Archive File are Correct"] -->
    FinalUpdateTasks["6. Final Update to `tasks.md`<br>(Mark Feature FULLY COMPLETED & ARCHIVED, link to archive file)"] -->
    UpdateProgressFile["7. Add Final Entry to `progress.md`<br>(Note archiving & link to archive file)"] -->
    ClearActiveCtx["8. Clear `activeContext.md`<br>Reset for Next Task/Project"] -->
    ArchiveDone["L3 Archiving Complete<br>Feature successfully documented and closed."]
```

## 📝 Structure for `documentation\memory-bank/archive/feature-[FeatureNameOrID]_YYYYMMDD.md`

*   **Feature Title:** (e.g., "Archive: User Profile Feature - Avatar Upload Enhancement")
*   **Feature ID (from `tasks.md`):**
*   **Date Archived:** YYYY-MM-DD
*   **Status:** COMPLETED & ARCHIVED
*   **1. Feature Overview:**
    *   Brief description of the feature and its purpose (can be extracted from `tasks.md` or `projectbrief.md`).
    *   Link to the original task entry/plan in `tasks.md` (if `tasks.md` is versioned or kept historically).
*   **2. Key Requirements Met:**
    *   List the main functional and non-functional requirements this feature addressed.
*   **3. Design Decisions & Creative Outputs:**
    *   Summary of key design choices.
    *   Direct links to all relevant `documentation\memory-bank/creative/creative-[aspect_name].md` documents.
    *   Link to `documentation\memory-bank/style-guide.md` version used (if applicable).
*   **4. Implementation Summary:**
    *   High-level overview of how the feature was implemented.
    *   List of primary new components/modules created.
    *   Key technologies or libraries utilized specifically for this feature.
    *   Link to the main feature branch merge commit or primary code location/pull request.
*   **5. Testing Overview:**
    *   Brief summary of the testing strategy employed for this feature (unit, integration, E2E).
    *   Outcome of the testing.
*   **6. Reflection & Lessons Learned:**
    *   Direct link to `documentation\memory-bank/reflection/reflection-[feature_id].md`.
    *   Optionally, copy 1-2 most critical lessons directly into the archive summary.
*   **7. Known Issues or Future Considerations (Optional, if any remaining from reflection):**
    *   Any minor known issues deferred.
    *   Potential future enhancements related to this feature.

### Key Files and Components Affected (from tasks.md)
[Summary or direct copy of file/component checklists from the original tasks.md for this project. This provides a quick reference to the scope of changes at a component/file level.]

## 📌 What to Emphasize in L3 Archiving

*   **Self-Contained Feature Record:** The goal is to have a go-to document in the archive that summarizes the "story" of this feature.
*   **Traceability:** Easy navigation from the archive summary to detailed planning, design, and reflection documents.
*   **Maintainability Focus:** Information that would help a future developer understand, maintain, or build upon this specific feature.
*   **Not a Full System Archive:** Unlike Level 4, this is not about archiving the entire application state, but rather the lifecycle of one significant feature.
```

---

**/isolation_rules/Level3/implementation-intermediate.mdc:**
```markdown
---
description: Implementation process for Level 3 intermediate features.
globs: implementation-intermediate.mdc
alwaysApply: false
---
# LEVEL 3 IMPLEMENTATION: BUILDING INTERMEDIATE FEATURES

> **TL;DR:** This guide focuses on the systematic implementation of a planned and designed Level 3 feature. It emphasizes modular development, strict adherence to creative decisions and the style guide, integration with existing systems, and thorough feature-specific testing.

## 🛠️ Level 3 Feature Implementation Workflow

This workflow outlines the typical steps for building an intermediate feature.

```mermaid
graph TD
    StartImpl["Start L3 Implementation"] -->
    ReviewDocs["1. Review All Relevant Docs<br>(Tasks, Creative Docs, Style Guide)"] -->
    SetupEnv["2. Setup/Verify Dev Environment<br>(Branch, Tools, Dependencies)"] -->
    ModuleBreakdown["3. Break Down Feature into Modules/Major Components<br>(Based on plan in `tasks.md`)"] -->
    BuildIterate["4. Implement Modules/Components Iteratively"]

    BuildIterate --> ImplementModule["4a. Select Next Module/Component"]
    ImplementModule --> CodeModule["4b. Code Module<br>(Adhere to design, style guide, coding standards)"]
    CodeModule --> UnitTests["4c. Write & Pass Unit Tests"]
    UnitTests --> SelfReview["4d. Self-Review/Code Linting"]
    SelfReview --> MoreModules{"4e. More Modules<br>for this Feature?"}
    MoreModules -- Yes --> ImplementModule

    MoreModules -- No --> IntegrateModules["5. Integrate All Feature Modules/Components"]
    IntegrateModules --> IntegrationTesting["6. Perform Integration Testing<br>(Feature modules + existing system parts)"]
    IntegrationTesting --> E2EFeatureTesting["7. End-to-End Feature Testing<br>(Validate against user stories & requirements)"]
    E2EFeatureTesting --> AccessibilityCheck["8. Accessibility & Responsiveness Check<br>(If UI is involved)"]
    AccessibilityCheck --> CodeCleanup["9. Code Cleanup & Refinement"]
    CodeCleanup --> UpdateMB["10. Update Memory Bank<br>(`tasks.md` sub-tasks, `progress.md` details)"]
    UpdateMB --> FinalFeatureReview["11. Final Feature Review (Conceptual Peer Review if possible)"]
    FinalFeatureReview --> ImplementationDone["L3 Implementation Complete<br>Ready for REFLECT Mode"]
```

## 🔑 Key Considerations for Level 3 Implementation

*   **Modularity & Encapsulation:** Design and build the feature in well-defined, reusable, and loosely coupled modules or components.
*   **Adherence to Design:** Strictly follow the decisions documented in `documentation\memory-bank/creative-*.md` files and the `documentation\memory-bank/style-guide.md`. Deviations must be justified and documented.
*   **State Management:** If the feature introduces or significantly interacts with complex application state, ensure the state management strategy (potentially defined in CREATIVE mode) is correctly implemented and tested.
*   **API Interactions:**
    *   If consuming new or existing APIs, ensure requests and responses are handled correctly, including error states.
    *   If exposing new API endpoints as part of the feature, ensure they are robust, secure, and documented.
*   **Error Handling:** Implement user-friendly error messages and robust error handling within the feature's scope.
*   **Performance:** Be mindful of performance implications. Avoid common pitfalls like N+1 database queries, inefficient algorithms, or large asset loading without optimization, especially if identified as a concern in the PLAN or CREATIVE phase.
*   **Security:** Implement with security best practices in mind, particularly for features handling user input, authentication, or sensitive data. Refer to any security design decisions from CREATIVE mode.

## 🧪 Testing Focus for Level 3 Features

*   **Unit Tests:** Each new function, method, or logical unit within the feature's components should have corresponding unit tests. Aim for good coverage of core logic and edge cases.
*   **Component Tests (for UI features):** Test UI components in isolation, verifying rendering, props handling, and event emissions.
*   **Integration Tests:** Crucial for L3. Test how the different modules/components of the new feature work together. Also, test how the completed feature integrates with existing parts of the application it interacts with.
*   **User Scenario / Acceptance Tests (Feature-Specific):** Validate that the feature fulfills its defined requirements and user stories from the user's perspective. This can be manual or automated.

## 📝 Documentation During Implementation

*   **`documentation\memory-bank/tasks.md`:** Update the status of sub-tasks related to the feature as they are completed. Note any blockers or changes in estimates.
*   **`documentation\memory-bank/progress.md`:** Make regular entries detailing:
    *   Modules/components completed.
    *   Key decisions made during implementation (if minor and not warranting a full CREATIVE cycle).
    *   Files significantly modified
    *   Test results for major integration points.
    *   Any deviations from the plan or creative designs, with rationale.
*   **Code Comments:** Write clear, concise comments explaining complex logic, assumptions, or TODOs.
*   **READMEs (if applicable):** If the feature introduces new modules or libraries that require specific setup or usage notes, consider adding or updating relevant README files.
```

---

**/isolation_rules/Level3/planning-comprehensive.mdc:**
```markdown
---
description: comprehensive planning for Level 3 tasks.
globs: planning-comprehensive.mdc
alwaysApply: false
---
# LEVEL 3 COMPREHENSIVE PLANNING

> **TL;DR:** This document provides structured planning guidelines for Level 3 (Intermediate Feature) tasks, focusing on comprehensive planning with creative phases and clear implementation strategies.

## 🏗️ PLANNING WORKFLOW

```mermaid
graph TD
    Start["Planning Start"] --> Req["📋 Requirements<br>Analysis"]
    Req --> Comp["🔍 Component<br>Analysis"]
    Comp --> Design["🎨 Design<br>Decisions"]
    Design --> Impl["⚙️ Implementation<br>Strategy"]
    Impl --> Test["🧪 Testing<br>Strategy"]
    Test --> Doc["📚 Documentation<br>Plan"]
    
    Design --> Creative["Creative Phases:"]
    Creative --> UI["UI/UX Design"]
    Creative --> Arch["Architecture"]
    Creative --> Algo["Algorithm"]
```

## 🔄 LEVEL TRANSITION HANDLING

```mermaid
graph TD
    L3["Level 3 Task"] --> Assess["Continuous<br>Assessment"]
    
    Assess --> Down["Downgrade to<br>Level 1/2"]
    Assess --> Up["Upgrade to<br>Level 4"]
    
    Down --> L12Trigger["Triggers:<br>- Simpler than expected<br>- Limited scope<br>- Few components"]
    
    Up --> L4Trigger["Triggers:<br>- System-wide impact<br>- Architectural changes<br>- High complexity"]
    
    L12Trigger --> L12Switch["Switch to<br>Level 1/2 Workflow"]
    L4Trigger --> L4Switch["Switch to<br>Level 4 Workflow"]
```

## 📋 PLANNING TEMPLATE

```markdown
# Feature Planning Document

## Requirements Analysis
- Core Requirements:
  - [ ] Requirement 1
  - [ ] Requirement 2
- Technical Constraints:
  - [ ] Constraint 1
  - [ ] Constraint 2

## Component Analysis
- Affected Components:
  - Component 1
    - Changes needed:
    - Dependencies:
  - Component 2
    - Changes needed:
    - Dependencies:

## Design Decisions
- Architecture:
  - [ ] Decision 1
  - [ ] Decision 2
- UI/UX:
  - [ ] Design 1
  - [ ] Design 2
- Algorithms:
  - [ ] Algorithm 1
  - [ ] Algorithm 2

## Implementation Strategy
1. Phase 1:
   - [ ] Task 1
   - [ ] Task 2
2. Phase 2:
   - [ ] Task 3
   - [ ] Task 4

## Testing Strategy
- Unit Tests:
  - [ ] Test 1
  - [ ] Test 2
- Integration Tests:
  - [ ] Test 3
  - [ ] Test 4

## Documentation Plan
- [ ] API Documentation
- [ ] User Guide Updates
- [ ] Architecture Documentation
```

## 🎨 CREATIVE PHASE IDENTIFICATION

```mermaid
graph TD
    subgraph "CREATIVE PHASES REQUIRED"
    UI["🎨 UI/UX Design<br>Required: Yes/No"]
    Arch["🏗️ Architecture Design<br>Required: Yes/No"]
    Algo["⚙️ Algorithm Design<br>Required: Yes/No"]
    end
    
    UI --> UITrig["Triggers:<br>- New UI Component<br>- UX Flow Change"]
    Arch --> ArchTrig["Triggers:<br>- System Structure Change<br>- New Integration"]
    Algo --> AlgoTrig["Triggers:<br>- Performance Critical<br>- Complex Logic"]
```

## ✅ VERIFICATION CHECKLIST

```mermaid
graph TD
    subgraph "PLANNING VERIFICATION"
    R["Requirements<br>Complete"]
    C["Components<br>Identified"]
    D["Design Decisions<br>Made"]
    I["Implementation<br>Plan Ready"]
    T["Testing Strategy<br>Defined"]
    Doc["Documentation<br>Plan Ready"]
    end
    
    R --> C --> D --> I --> T --> Doc
```

## 🔄 IMPLEMENTATION PHASES

```mermaid
graph LR
    Setup["🛠️ Setup"] --> Core["⚙️ Core<br>Implementation"]
    Core --> UI["🎨 UI<br>Implementation"]
    UI --> Test["🧪 Testing"]
    Test --> Doc["📚 Documentation"]
```

## 🚨 PLANNING EFFICIENCY PRINCIPLE

Remember:

```
┌─────────────────────────────────────────────────────┐
│ Level 3 planning requires COMPREHENSIVE DESIGN but   │
│ should avoid OVER-ENGINEERING. Focus on delivering  │
│ maintainable, well-documented features.            │
└─────────────────────────────────────────────────────┘
```
```

---

**/isolation_rules/Level3/reflection-intermediate.mdc:**
```markdown
---
description: Reflection process for Level 3 intermediate features.
globs: reflection-intermediate.mdc
alwaysApply: false
---
# LEVEL 3 REFLECTION: INTERMEDIATE FEATURE REVIEW

> **TL;DR:** This guide structures the reflection process for a completed Level 3 intermediate feature. The focus is on a detailed review of the entire feature development lifecycle, from planning and design through implementation and testing, to extract meaningful lessons and identify improvements for future feature work.

## 🔍 Level 3 Reflection Process

The goal is to create a comprehensive `documentation\memory-bank/reflection/reflection-[feature_id].md` document.

```mermaid
graph TD
    StartReflect["Start L3 Reflection"] -->
    ReviewDocs["1. Review All Gathered Documentation"] -->
    AssessOutcome["2. Assess Overall Feature Outcome<br>Did it meet all requirements from tasks.md? Was it successful?"] -->
    AnalyzePlan["3. Analyze Planning Phase Effectiveness<br>Was planning-comprehensive.mdc guidance effective? Was the plan accurate? Scope creep?"] -->
    AnalyzeCreative["4. Analyze Creative Phase(s) Effectiveness<br>Were design decisions sound? Did they translate well to implementation? Issues?"] -->
    AnalyzeImpl["5. Analyze Implementation Phase<br>What went well? Challenges? Bottlenecks? Adherence to design/style guide?"] -->
    AnalyzeTesting["6. Analyze Testing Phase<br>Were tests adequate? Bugs found post-release (if applicable)? Test coverage feel right?"] -->
    IdentifyLessons["7. Identify Key Lessons Learned<br>(Technical, Process, Teamwork, Estimation)"] -->
    ProposeImprovements["8. Propose Actionable Improvements<br>For future L3 feature development"] -->
    DraftReflectionDoc["9. Draft `reflection-[feature_id].md`<br>Using structured template"] -->
    FinalizeReflection["10. Finalize & Save Reflection Document"] -->
    UpdateTasksStatus["11. Update `tasks.md`<br>Mark L3 Reflection Complete"] -->
    ReflectionDone["L3 Reflection Complete<br>Ready for ARCHIVE Mode"]
```

## 📝 Structure for `documentation\memory-bank/reflection-[feature_id].md`

*   **Feature Name & ID:**
*   **Date of Reflection:**
*   **Brief Feature Summary:** (What was built?)
*   **1. Overall Outcome & Requirements Alignment:**
    *   How well did the final feature meet the initial requirements?
    *   Were there any deviations from the original scope? If so, why?
    *   What is the overall assessment of the feature's success?
*   **2. Planning Phase Review:**
    *   How effective was the guidance from `Level3/planning-comprehensive.mdc`?
    *   Was the initial plan in `tasks.md` (component breakdown, strategy, risks) accurate and helpful?
    *   What could have been planned better? Were estimations (if made) accurate?
*   **3. Creative Phase(s) Review (if applicable):**
    *   Were the right aspects flagged for CREATIVE mode?
    *   How effective were the design decisions made in `creative-*.md` documents?
    *   Did these designs translate well into practical implementation? Any friction points?
    *   Was `documentation\memory-bank/style-guide.md` clear and sufficient for UI aspects?
*   **4. Implementation Phase Review:**
    *   What were the major successes during implementation? (e.g., efficient module development, good use of libraries)
    *   What were the biggest challenges or roadblocks? How were they overcome?
    *   Were there any unexpected technical difficulties or complexities?
    *   How was adherence to the style guide and coding standards?
*   **5. Testing Phase Review:**
    *   Was the testing strategy (unit, integration, E2E for the feature) effective?
    *   Did testing uncover significant issues early enough?
    *   What could improve the testing process for similar features?
*   **6. What Went Well? (Highlight 3-5 key positives across all phases for this feature)**
*   **7. What Could Have Been Done Differently? (Identify 3-5 areas for improvement)**
*   **8. Key Lessons Learned:**
    *   **Technical:** New insights about technologies, patterns, or architecture used for this feature.
    *   **Process:** Insights about the L3 workflow, communication, task management.
    *   **Estimation (if applicable):** Lessons about estimating work for features of this scale.
*   **9. Actionable Improvements for Future L3 Features:** (Specific suggestions)

## 🎯 Focus Areas for L3 Reflection

*   **Feature Scope Management:** Was the scope well-defined and managed?
*   **Integration Complexity:** Challenges or successes in integrating the feature with the existing application.
*   **Design-to-Implementation Fidelity:** How closely did the final product match the designs?
*   **Cross-Component Impact:** Understanding the ripple effects of the feature.
```

---

**/isolation_rules/Level3/task-tracking-intermediate.mdc:**
```markdown
---
description: intermediate task tracking for Level 3 tasks.
globs: task-tracking-intermediate.mdc
alwaysApply: false
---
# LEVEL 3 INTERMEDIATE TASK TRACKING

> **TL;DR:** This document provides structured task tracking guidelines for Level 3 (Intermediate Feature) tasks, using visual tracking elements and clear checkpoints.

## 🔍 TASK TRACKING WORKFLOW

```mermaid
graph TD
    Start["Task Start"] --> Init["📋 Initialize<br>Task Entry"]
    Init --> Struct["🏗️ Create Task<br>Structure"]
    Struct --> Track["📊 Progress<br>Tracking"]
    Track --> Update["🔄 Regular<br>Updates"]
    Update --> Complete["✅ Task<br>Completion"]
    
    Struct --> Components["Components:"]
    Components --> Req["Requirements"]
    Components --> Steps["Implementation<br>Steps"]
    Components --> Creative["Creative Phase<br>Markers"]
    Components --> Check["Checkpoints"]
    
    Track --> Status["Track Status:"]
    Status --> InProg["🔄 In Progress"]
    Status --> Block["⛔ Blocked"]
    Status --> Done["✅ Complete"]
    Status --> Skip["⏭️ Skipped"]
```

## 📋 TASK ENTRY TEMPLATE

```markdown
# [Task Title]

## Requirements
- [ ] Requirement 1
- [ ] Requirement 2
- [ ] Requirement 3

## Components Affected
- Component 1
- Component 2
- Component 3

## Implementation Steps
1. [ ] Step 1
2. [ ] Step 2
3. [ ] Step 3

## Creative Phases Required
- [ ] 🎨 UI/UX Design
- [ ] 🏗️ Architecture Design
- [ ] ⚙️ Algorithm Design

## Checkpoints
- [ ] Requirements verified
- [ ] Creative phases completed
- [ ] Implementation tested
- [ ] Documentation updated

## Current Status
- Phase: [Current Phase]
- Status: [In Progress/Blocked/Complete]
- Blockers: [If any]
```

## 🔄 PROGRESS TRACKING VISUALIZATION

```mermaid
graph TD
    subgraph "TASK PROGRESS"
    P1["✓ Requirements<br>Defined"]
    P2["✓ Components<br>Identified"]
    P3["→ Creative Phase<br>In Progress"]
    P4["□ Implementation"]
    P5["□ Testing"]
    P6["□ Documentation"]
    end
```

## ✅ UPDATE PROTOCOL

```mermaid
sequenceDiagram
    participant Task as Task Entry
    participant Status as Status Update
    participant Creative as Creative Phase
    participant Implementation as Implementation
    
    Task->>Status: Update Progress
    Status->>Creative: Flag for Creative Phase
    Creative->>Implementation: Complete Design
    Implementation->>Status: Update Status
    Status->>Task: Mark Complete
```

## 🎯 CHECKPOINT VERIFICATION

| Phase | Verification Items | Status |
|-------|-------------------|--------|
| Requirements | All requirements documented | [ ] |
| Components | Affected components listed | [ ] |
| Creative | Design decisions documented | [ ] |
| Implementation | Code changes tracked | [ ] |
| Testing | Test results recorded | [ ] |
| Documentation | Updates completed | [ ] |
```

---

**/isolation_rules/Phases/CreativePhase/creative-phase-architecture.mdc:**
```markdown
---
description: creative phase architecture
globs: creative-phase-architecture.md
alwaysApply: false
---

# CREATIVE PHASE: ARCHITECTURE DESIGN

> **TL;DR:** This document provides structured guidance for architectural design decisions during creative phases, ensuring comprehensive evaluation of options and clear documentation of architectural choices.

## 🏗️ ARCHITECTURE DESIGN WORKFLOW

```mermaid
graph TD
    Start["Architecture<br>Design Start"] --> Req["1. Requirements<br>Analysis"]
    Req --> Comp["2. Component<br>Identification"]
    Comp --> Options["3. Architecture<br>Options"]
    Options --> Eval["4. Option<br>Evaluation"]
    Eval --> Decision["5. Decision &<br>Documentation"]
    Decision --> Valid["6. Validation &<br>Verification"]
```

## 📋 ARCHITECTURE DECISION TEMPLATE

```markdown
# Architecture Decision Record

## Context
- System Requirements:
  - [Requirement 1]
  - [Requirement 2]
- Technical Constraints:
  - [Constraint 1]
  - [Constraint 2]

## Component Analysis
- Core Components:
  - [Component 1]: [Purpose/Role]
  - [Component 2]: [Purpose/Role]
- Interactions:
  - [Interaction 1]
  - [Interaction 2]

## 🧠 Architecture Options & Research

**Instructions:** For each potential library or framework, use MCP tools (`read_wiki_structure`, `ask_question`, `read_wiki_contents`) to gather data.

### Option 1: [Name]
- Description: [Brief description]
- **Research Insights**: [Summary of findings from MCP tools for this option]
- Pros:
  - [Pro 1]
  - [Pro 2]
- Cons:
  - [Con 1]
  - [Con 2]
- Technical Fit: [High/Medium/Low]
- Complexity: [High/Medium/Low]
- Scalability: [High/Medium/Low]

### Option 2: [Name]
- Description: [Brief description]
- **Research Insights**: [Summary of findings from MCP tools for this option]
[Same structure as Option 1]

## Decision
- Chosen Option: [Option name]
- Rationale: [Explanation, referencing research insights where applicable]
- Implementation Considerations:
  - [Consideration 1]
  - [Consideration 2]

## Validation
- Requirements Met:
  - [✓] Requirement 1
  - [✓] Requirement 2
- Technical Feasibility: [Assessment]
- Risk Assessment: [Evaluation]
```

## 🎯 ARCHITECTURE EVALUATION CRITERIA

```mermaid
graph TD
    subgraph "EVALUATION CRITERIA"
    C1["Scalability"]
    C2["Maintainability"]
    C3["Performance"]
    C4["Security"]
    C5["Cost"]
    C6["Time to Market"]
    end
```

## 📊 ARCHITECTURE VISUALIZATION TEMPLATES

### Component Diagram Template
```mermaid
graph TD
    subgraph "SYSTEM ARCHITECTURE"
    C1["Component 1"]
    C2["Component 2"]
    C3["Component 3"]
    
    C1 -->|"Interface 1"| C2
    C2 -->|"Interface 2"| C3
    end
```

### Data Flow Template
```mermaid
sequenceDiagram
    participant C1 as Component 1
    participant C2 as Component 2
    participant C3 as Component 3
    
    C1->>C2: Request
    C2->>C3: Process
    C3-->>C2: Response
    C2-->>C1: Result
```

## ✅ VERIFICATION CHECKLIST

```markdown
## Architecture Design Verification
- [ ] All system requirements addressed
- [ ] Component responsibilities defined
- [ ] Interfaces specified
- [ ] Data flows documented
- [ ] Security considerations addressed
- [ ] Scalability requirements met
- [ ] Performance requirements met
- [ ] Maintenance approach defined

## Implementation Readiness
- [ ] All components identified
- [ ] Dependencies mapped
- [ ] Technical constraints documented
- [ ] Risk assessment completed
- [ ] Resource requirements defined
- [ ] Timeline estimates provided
```

## 🔄 ARCHITECTURE REVIEW PROCESS

```mermaid
graph TD
    subgraph "REVIEW PROCESS"
    R1["Technical<br>Review"]
    R2["Security<br>Review"]
    R3["Performance<br>Review"]
    R4["Final<br>Approval"]
    end
    
    R1 --> R2 --> R3 --> R4
```
```

---

**/isolation_rules/Phases/CreativePhase/optimized-creative-template.mdc:**
```markdown
---
description: Optimized creative phase template with progressive documentation
globs: "**/creative*/**", "**/design*/**", "**/decision*/**"
alwaysApply: false
---

# OPTIMIZED CREATIVE PHASE TEMPLATE

> **TL;DR:** This template implements a progressive documentation approach for creative phases, optimizing token usage while maintaining thorough design exploration.

## 📝 PROGRESSIVE DOCUMENTATION MODEL

```mermaid
graph TD
    Start["Creative Phase Start"] --> P1["1️⃣ PROBLEM<br>Define scope"]
    P1 --> P2["2️⃣ OPTIONS<br>Explore alternatives"]
    P2 --> P3["3️⃣ ANALYSIS<br>Evaluate selected options"]
    P3 --> P4["4️⃣ DECISION<br>Finalize approach"]
    P4 --> P5["5️⃣ IMPLEMENTATION<br>Document guidelines"]
```

## 📋 TEMPLATE STRUCTURE

```markdown
📌 CREATIVE PHASE START: [Component Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1️⃣ PROBLEM
   Description: [Brief problem description]
   Requirements: [Key requirements as bullet points]
   Constraints: [Technical or business constraints]

2️⃣ OPTIONS
   Option A: [Name] - [One-line description]
   Option B: [Name] - [One-line description]
   Option C: [Name] - [One-line description]

3️⃣ ANALYSIS
   | Criterion | Option A | Option B | Option C |
   |-----------|----------|----------|----------|
   | Performance | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐ |
   | Complexity | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
   | Maintainability | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ |
   
   Key Insights:
   - [Insight 1]
   - [Insight 2]

4️⃣ DECISION
   Selected: [Option X]
   Rationale: [Brief justification]
   
5️⃣ IMPLEMENTATION NOTES
   - [Implementation note 1]
   - [Implementation note 2]
   - [Implementation note 3]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📌 CREATIVE PHASE END
```

## 🧩 DETAILED OPTION ANALYSIS (ON DEMAND)

Detailed analysis can be provided on demand for selected options using Markdown `<details>` tags:

```markdown
<details>
  <summary>Detailed Analysis: Option A</summary>
  
  ### Option A: [Full Name]
  
  **Complete Description**:
  [Detailed description of how the option works]
  
  **Pros**:
  - [Pro 1 with explanation]
  - [Pro 2 with explanation]
  - [Pro 3 with explanation]
  
  **Cons**:
  - [Con 1 with explanation]
  - [Con 2 with explanation]
  
  **Implementation Complexity**: [Low/Medium/High]
  [Explanation of complexity factors]
  
  **Resource Requirements**:
  [Details on resource needs]
  
  **Risk Assessment**:
  [Analysis of risks]
</details>
```

## 📊 COMPLEXITY-BASED SCALING

The template automatically scales documentation requirements based on task complexity level:

### Level 1-2 (Quick Fix/Enhancement)
- Simplified problem/solution
- Focus on implementation
- Minimal option exploration

### Level 3 (Feature Development)
- Multiple options required
- Analysis table with key criteria
- Implementation guidelines

### Level 4 (Enterprise Development)
- Comprehensive analysis
- Multiple viewpoints considered
- Detailed implementation plan
- Expanded verification criteria

## ✅ VERIFICATION PROTOCOL

Quality verification is condensed into a simple checklist:

```markdown
VERIFICATION:
[x] Problem clearly defined
[x] Multiple options considered
[x] Decision made with rationale
[x] Implementation guidance provided
```

## 🔄 USAGE EXAMPLES

### Architecture Decision (Level 3)

```markdown
📌 CREATIVE PHASE START: Authentication System
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1️⃣ PROBLEM
   Description: Design an authentication system for the application
   Requirements: Secure, scalable, supports SSO, easy to maintain
   Constraints: Must work with existing user database, <100ms response time

2️⃣ OPTIONS
   Option A: JWT-based stateless auth - Simple token-based approach
   Option B: Session-based auth with Redis - Server-side session storage
   Option C: OAuth2 implementation - Delegated authorization framework

3️⃣ ANALYSIS
   | Criterion | JWT | Sessions | OAuth2 |
   |-----------|-----|----------|--------|
   | Security | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
   | Scalability | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
   | Complexity | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
   | Performance | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
   
   Key Insights:
   - JWT offers best performance but limited revocation options
   - Sessions provide better security control but require more infrastructure
   - OAuth2 most complex but offers best integration possibilities

4️⃣ DECISION
   Selected: Option A: JWT-based auth with refresh tokens
   Rationale: Best balance of performance and scalability while meeting security needs
   
5️⃣ IMPLEMENTATION NOTES
   - Use HS256 algorithm for token signing
   - Implement short-lived access tokens (15min) with longer refresh tokens (7 days)
   - Store token blacklist in Redis for revocation capability
   - Add rate limiting on token endpoints

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📌 CREATIVE PHASE END
```

### Algorithm Decision (Level 2)

```markdown
📌 CREATIVE PHASE START: Search Algorithm
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1️⃣ PROBLEM
   Description: Implement efficient text search for product catalog
   Requirements: Fast results, support for partial matches, case insensitive
   Constraints: Dataset < 10,000 items, must work in browser environment

2️⃣ OPTIONS
   Option A: Simple regex search - Basic pattern matching
   Option B: Trie-based search - Prefix tree structure
   Option C: Fuzzy search with Levenshtein - Edit distance algorithm

3️⃣ DECISION
   Selected: Option B: Trie-based search
   Rationale: Best performance for prefix searches with manageable memory usage
   
4️⃣ IMPLEMENTATION NOTES
   - Use existing trie library
   - Preprocess text to lowercase during indexing
   - Implement letter-by-letter search for instant results
   - Add debounce (300ms) to prevent excessive rebuilding

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📌 CREATIVE PHASE END
```

## 🏆 TOKEN EFFICIENCY BENEFITS

This template significantly reduces token usage by:

1.  Focusing on essential information without unnecessary verbosity
2.  Using compact tabular formats for comparisons
3.  Implementing progressive disclosure for detailed information
4.  Scaling documentation requirements by task complexity
5.  Using visual indicators (emojis) for quick scanning
```

---

**/isolation_rules/main-optimized.mdc:**
```markdown
---
description: Optimized main rule for improved token efficiency
globs: main-optimized.mdc
alwaysApply: false
---
# 🔍 OPTIMIZED MEMORY BANK SYSTEM

🚨 CRITICAL RULE: MEMORY BANK CREATION IS MANDATORY 🚨
Memory Bank MUST be created BEFORE any other operation in ANY mode
NO process can continue without verifying Memory Bank existence

> **TL;DR:** This system uses optimized context management and adaptive rule loading to maximize token efficiency while preserving the structured development approach.

## 🧭 OPTIMIZED MODE ARCHITECTURE

```mermaid
graph TD
    subgraph "Memory Bank Core"
        Context["Context Manager"]
        Rules["Rule Loader"]
        FileIO["File Manager"]
        Transition["Mode Transition"]
    end
    
    subgraph "Custom Modes"
        VAN["VAN<br>Initialization"]
        PLAN["PLAN<br>Planning"]
        CREATIVE["CREATIVE<br>Design"]
        IMPLEMENT["IMPLEMENT<br>Building"]
        REFLECT["REFLECT<br>Review"]
        ARCHIVE["ARCHIVE<br>Documentation"]
    end
    
    Context --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
    Rules --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
    FileIO --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
    Transition --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
    
    VAN --> PLAN
    PLAN --> CREATIVE
    CREATIVE --> IMPLEMENT
    IMPLEMENT --> REFLECT
    REFLECT --> ARCHIVE
```

## 📈 ADAPTIVE COMPLEXITY MODEL

```mermaid
graph TD
    Task["Task Creation"] --> Complexity{"Complexity<br>Level?"}
    
    Complexity -->|"Level 1<br>Quick Fix"| L1["3-Phase<br>Streamlined Process"]
    Complexity -->|"Level 2<br>Enhancement"| L2["4-Phase<br>Balanced Process"]
    Complexity -->|"Level 3<br>Feature"| L3["5-Phase<br>Comprehensive Process"]
    Complexity -->|"Level 4<br>Enterprise"| L4["6-Phase<br>Governance Process"]
    
    L1 --> L1_Process["VAN → IMPLEMENT → REFLECT"]
    L2 --> L2_Process["VAN → PLAN → IMPLEMENT → REFLECT"]
    L3 --> L3_Process["VAN → PLAN → CREATIVE → IMPLEMENT → REFLECT"]
    L4 --> L4_Process["VAN → PLAN → CREATIVE → IMPLEMENT → REFLECT → ARCHIVE"]
```

## 🧠 HIERARCHICAL RULE LOADING

Rules are loaded hierarchically to optimize context usage. Refer to `Core/hierarchical-rule-loading.mdc` for full details.

```mermaid
graph TD
    Root["Memory Bank<br>Common Rules"] --> Core["Core Rules<br>Shared Across Modes"]
    
    Core --> L1["Level 1<br>Rules"]
    Core --> L2["Level 2<br>Rules"]
    Core --> L3["Level 3<br>Rules"]
    Core --> L4["Level 4<br>Rules"]
    
    Core --> VM["Mode<br>Visual Maps"]
    
    Core --> Phase["Phase-Specific<br>Rules"]
    
    Phase --> VAN_Rules["VAN Mode<br>Rules"]
    Phase --> PLAN_Rules["PLAN Mode<br>Rules"]
    Phase --> CREATIVE_Rules["CREATIVE Mode<br>Rules"]
    Phase --> IMPLEMENT_Rules["IMPLEMENT Mode<br>Rules"]
    Phase --> REFLECT_Rules["REFLECT Mode<br>Rules"]
    Phase --> ARCHIVE_Rules["ARCHIVE Mode<br>Rules"]
```

## 🔄 TOKEN-OPTIMIZED CREATIVE PHASE

Creative phase documentation is progressively generated. Refer to `Phases/CreativePhase/optimized-creative-template.mdc`.

```mermaid
graph TD
    Start["Creative Phase<br>Initiation"] --> P1["1️⃣ PROBLEM<br>Define scope"]
    P1 --> P2["2️⃣ OPTIONS<br>List alternatives"]
    P2 --> P3["3️⃣ ANALYSIS<br>Compare options"]
    P3 --> P4["4️⃣ DECISION<br>Select approach"]
    P4 --> P5["5️⃣ GUIDELINES<br>Document implementation"]
    
    P3 -.->|"On Demand"| Details["Detailed Option<br>Analysis"]
    
```

## 🔀 OPTIMIZED MODE TRANSITIONS

Mode transitions use a unified context transfer protocol. Refer to `Core/mode-transition-optimization.mdc`.

```mermaid
sequenceDiagram
    participant Current as Current Mode
    participant Context as Context Manager
    participant Next as Next Mode
    
    Current->>Context: Create transition document
    Current->>Context: Store critical context
    Context->>Context: Prepare rule cache
    Current->>Next: Initiate transition
    Next->>Context: Verify context availability
    Context->>Next: Load relevant context
    Context->>Next: Load cached rules
    Next->>Next: Continue with preserved context
```

## 📊 MEMORY BANK EFFICIENT UPDATES

Memory Bank updates are optimized using differential changes.

```mermaid
graph TD
    subgraph "Memory Bank Files"
        tasks["tasks.md<br>Source of Truth"]
        active["activeContext.md<br>Current Focus"]
        creative["creative-*.md<br>Design Decisions"]
        progress["progress.md<br>Implementation Status"]
        transition["transition.md<br>Mode Transitions"]
    end
    
    Update["Update Request"] --> Diff{"Changed?"}
    Diff -->|"No"| Skip["Skip Update"]
    Diff -->|"Yes"| Section{"Section<br>Change?"}
    Section -->|"Yes"| Partial["Update Changed<br>Sections Only"]
    Section -->|"No"| Full["Full File<br>Update"]
    
    Partial --> tasks
    Full --> tasks
```

## 💻 COMPLEXITY-BASED DOCUMENTATION

Documentation requirements scale based on complexity level:

| Documentation | Level 1 | Level 2 | Level 3 | Level 4 |
|---------------|---------|---------|---------|---------|
| Problem Definition | Brief | Standard | Detailed | Comprehensive |
| Options Analysis | Optional | Basic | Multiple Options | Extensive |
| Implementation Plan | Simple | Standard | Detailed | Phased |
| Testing Requirements | Basic | Standard | Comprehensive | Rigorous |
| Documentation | Minimal | Standard | Detailed | Extensive |

## 📑 OPTIMIZED TEMPLATES BY LEVEL

*   **Level 1: Quick Fix Template** (See `Level1/optimized-workflow-level1.mdc`)
*   **Level 2: Enhancement Template** (See `Level2/workflow-level2.mdc`)
*   **Level 3-4: Comprehensive Template** (Uses `Phases/CreativePhase/optimized-creative-template.mdc` with appropriate depth)

## 🔄 REFERENCE MAPS

Each mode's visual process map is optimized for token efficiency:

-   [VAN Mode Map](mdc:isolation_rules/visual-maps/van-mode-map.mdc)
-   [PLAN Mode Map](mdc:isolation_rules/visual-maps/plan-mode-map.mdc)
-   [CREATIVE Mode Map](mdc:isolation_rules/visual-maps/creative-mode-map.mdc)
-   [IMPLEMENT Mode Map](mdc:isolation_rules/visual-maps/implement-mode-map.mdc)
-   [REFLECT Mode Map](mdc:isolation_rules/visual-maps/reflect-mode-map.mdc)
-   [ARCHIVE Mode Map](mdc:isolation_rules/visual-maps/archive-mode-map.mdc)

## ⚡ TOKEN EFFICIENCY IMPROVEMENTS

This optimized system achieves token efficiency through:

1.  Hierarchical rule loading.
2.  Progressive creative phase documentation.
3.  Context preservation during mode transitions.
4.  Differential Memory Bank updates.
5.  Complexity-based template scaling.

## 💡 USAGE GUIDANCE

To use the optimized system:

1.  Start with the `VAN` command to initialize and determine complexity.
2.  Follow the complexity-appropriate workflow (guides you to `PLAN`, `CREATIVE`, `IMPLEMENT`, `REFLECT`, `ARCHIVE`).
3.  Use progressive documentation appropriate to task complexity.
4.  The system manages rule loading and context preservation automatically.
```

---

**/isolation_rules/visual-maps/archive-mode-map.mdc:**
```markdown
---
description: Visual process map for ARCHIVE mode (Task Documentation)
globs: "**/archive*/**", "**/document*/**", "**/complete*/**"
alwaysApply: false
---

# ARCHIVE MODE: TASK DOCUMENTATION PROCESS MAP

> **TL;DR:** This visual map guides the ARCHIVE mode process, focusing on creating comprehensive documentation of the completed task, archiving relevant files, and updating the Memory Bank for future reference.

## 🧭 ARCHIVE MODE PROCESS FLOW

```mermaid
graph TD
    Start["START ARCHIVE MODE"] --> ReadTasks["Read tasks.md<br>reflection.md and<br>progress.md"]
    
    %% Initial Assessment
    ReadTasks --> VerifyReflect{"Reflection<br>Complete?"}
    VerifyReflect -->|"No"| ReturnReflect["Return to<br>REFLECT Mode"]
    VerifyReflect -->|"Yes"| AssessLevel{"Determine<br>Complexity Level"}
    
    %% Level-Based Archiving
    AssessLevel -->|"Level 1"| L1Archive["LEVEL 1 ARCHIVING<br>Level1/archive-minimal.md (Conceptual)"]
    AssessLevel -->|"Level 2"| L2Archive["LEVEL 2 ARCHIVING<br>Level2/archive-basic.md"]
    AssessLevel -->|"Level 3"| L3Archive["LEVEL 3 ARCHIVING<br>Level3/archive-intermediate.md"]
    AssessLevel -->|"Level 4"| L4Archive["LEVEL 4 ARCHIVING<br>Level4/archive-comprehensive.md (Conceptual)"]
    
    %% Level 1 Archiving (Minimal) - Handled by Level 1 workflow
    L1Archive --> L1Summary["Create Quick<br>Summary in tasks.md"]
    L1Summary --> L1Complete["Mark Task<br>Complete"]
    
    %% Level 2 Archiving (Basic) - Handled by Level 2 workflow (archive-basic.mdc)
    L2Archive --> L2Summary["Create Basic<br>Archive Document"]
    L2Summary --> L2Doc["Document<br>Changes"]
    L2Doc --> L2Task["Update<br>tasks.md"]
    L2Task --> L2Progress["Update<br>progress.md"]
    L2Progress --> L2Complete["Mark Task<br>Complete"]
    
    %% Level 3-4 Archiving (Comprehensive) - Handled by Level 3 workflow (archive-intermediate.mdc)
    L3Archive & L4Archive --> L34Summary["Create Comprehensive<br>Archive Document"]
    L34Summary --> L34Doc["Document<br>Implementation"]
    L34Doc --> L34Creative["Archive Creative<br>Phase Documents"]
    L34Creative --> L34Code["Document Code<br>Changes"]
    L34Code --> L34Test["Document<br>Testing"]
    L34Test --> L34Lessons["Summarize<br>Lessons Learned"]
    L34Lessons --> L34Task["Update<br>tasks.md"]
    L34Task --> L34Progress["Update<br>progress.md"]
    L34Progress --> L34System["Update System<br>Documentation"]
    L34System --> L34Complete["Mark Task<br>Complete"]
    
    %% Completion
    L1Complete & L2Complete & L34Complete --> CreateArchive["Create Archive<br>Document in<br>docs/archive/"]
    CreateArchive --> UpdateActive["Update<br>activeContext.md"]
    UpdateActive --> Reset["Reset for<br>Next Task"]
```

## 📋 ARCHIVE DOCUMENT STRUCTURE

The archive document should follow this structured format:

```mermaid
graph TD
    subgraph "Archive Document Structure"
        Header["# TASK ARCHIVE: [Task Name]"]
        Meta["## METADATA<br>Task info, dates, complexity"]
        Summary["## SUMMARY<br>Brief overview of the task"]
        Requirements["## REQUIREMENTS<br>What the task needed to accomplish"]
        Implementation["## IMPLEMENTATION<br>How the task was implemented"]
        Testing["## TESTING<br>How the solution was verified"]
        Lessons["## LESSONS LEARNED<br>Key takeaways from the task"]
        Refs["## REFERENCES<br>Links to related documents"]
    end
    
    Header --> Meta --> Summary --> Requirements --> Implementation --> Testing --> Lessons --> Refs
```

## 📊 REQUIRED FILE STATE VERIFICATION

Before archiving can begin, verify file state:

```mermaid
graph TD
    Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>reflection<br>complete?"}
    
    CheckTasks -->|"No"| ErrorReflect["ERROR:<br>Return to REFLECT Mode"]
    CheckTasks -->|"Yes"| CheckReflection{"reflection.md<br>exists?"}
    
    CheckReflection -->|"No"| ErrorCreate["ERROR:<br>Create reflection.md first"]
    CheckReflection -->|"Yes"| CheckProgress{"progress.md<br>updated?"}
    
    CheckProgress -->|"No"| ErrorProgress["ERROR:<br>Update progress.md first"]
    CheckProgress -->|"Yes"| ReadyArchive["Ready for<br>Archiving"]
```

## 🔍 ARCHIVE TYPES BY COMPLEXITY

```mermaid
graph TD
    subgraph "Level 1: Minimal Archive (in tasks.md)"
        L1A["Basic Bug<br>Description"]
        L1B["Solution<br>Summary"]
        L1C["Affected<br>Files"]
    end
    
    subgraph "Level 2: Basic Archive (archive-basic.mdc)"
        L2A["Enhancement<br>Description"]
        L2B["Implementation<br>Summary"]
        L2C["Testing<br>Results"]
        L2D["Lessons<br>Learned"]
    end
    
    subgraph "Level 3-4: Comprehensive Archive (archive-intermediate.mdc / comprehensive)"
        L3A["Detailed<br>Requirements"]
        L3B["Architecture/<br>Design Decisions"]
        L3C["Implementation<br>Details"]
        L3D["Testing<br>Strategy"]
        L3E["Performance<br>Considerations"]
        L3F["Future<br>Enhancements"]
        L3G["Cross-References<br>to Other Systems"]
    end
    
    L1A --> L1B --> L1C
    
    L2A --> L2B --> L2C --> L2D
    
    L3A --> L3B --> L3C --> L3D --> L3E --> L3F --> L3G
```

## 📝 ARCHIVE DOCUMENT TEMPLATES

### Level 1 (Minimal) Archive (Integrated into tasks.md)
```markdown
# Bug Fix Archive: [Bug Name] (within tasks.md)

## Date
[Date of fix]

## Summary
[Brief description of the bug and solution]

## Implementation
[Description of the fix implemented]

## Files Changed
- [File 1]
- [File 2]
```

### Levels 2 (Basic) Archive (See `Level2/archive-basic.mdc`)
### Levels 3-4 (Comprehensive) Archive (See `Level3/archive-intermediate.mdc` or equivalent Level 4)

## 📋 ARCHIVE LOCATION AND NAMING

Archive documents should be organized following this pattern:

```mermaid
graph TD
    subgraph "Archive Structure"
        Root["docs/archive/"]
        Tasks["tasks/"]
        Features["features/"]
        Systems["systems/"]
        
        Root --> Tasks
        Root --> Features
        Root --> Systems
        
        Tasks --> Bug["bug-fix-name-YYYYMMDD.md"]
        Tasks --> Enhancement["enhancement-name-YYYYMMDD.md"]
        Features --> Feature["feature-name-YYYYMMDD.md"]
        Systems --> System["system-name-YYYYMMDD.md"]
    end
```

## 📊 TASKS.MD FINAL UPDATE

When archiving is complete, update `tasks.md` with:

```
## Status
- [x] Initialization complete
- [x] Planning complete
[For Level 3-4:]
- [x] Creative phases complete
- [x] Implementation complete
- [x] Reflection complete
- [x] Archiving complete

## Archive
- **Date**: [Completion date]
- **Archive Document**: [Link to archive document]
- **Status**: COMPLETED
```

## 📋 ARCHIVE VERIFICATION CHECKLIST

```
✓ ARCHIVE VERIFICATION
- Reflection document reviewed? [YES/NO]
- Archive document created with all sections? [YES/NO]
- Archive document placed in correct location? [YES/NO]
- tasks.md marked as completed? [YES/NO]
- progress.md updated with archive reference? [YES/NO]
- activeContext.md updated for next task? [YES/NO]
- Creative phase documents archived (Level 3-4)? [YES/NO/NA]

→ If all YES: Archiving complete - Memory Bank reset for next task
→ If any NO: Complete missing archive elements
```

## 🔄 TASK COMPLETION NOTIFICATION

When archiving is complete, notify user with:

```
## TASK ARCHIVED

✅ Archive document created in docs/archive/
✅ All task documentation preserved
✅ Memory Bank updated with references
✅ Task marked as COMPLETED

→ Memory Bank is ready for the next task
→ To start a new task, use VAN MODE
```
```

---

**/isolation_rules/visual-maps/creative-mode-map.mdc:**
```markdown
---
description: Visual process map for CREATIVE mode (Design Decisions)
globs: "**/creative*/**", "**/design*/**", "**/decision*/**"
alwaysApply: false
---

# CREATIVE MODE: DESIGN PROCESS MAP

> **TL;DR:** This visual map guides the CREATIVE mode process, focusing on structured design decision-making for components that require deeper exploration before implementation.

## 🧭 CREATIVE MODE PROCESS FLOW

```mermaid
graph TD
    Start["START CREATIVE MODE"] --> ReadTasks["Read tasks.md<br>For Creative Requirements"]
    
    %% Initial Assessment
    ReadTasks --> VerifyPlan{"Plan Complete<br>& Creative Phases<br>Identified?"}
    VerifyPlan -->|"No"| ReturnPlan["Return to<br>PLAN Mode"]
    VerifyPlan -->|"Yes"| IdentifyPhases["Identify Creative<br>Phases Required"]
    
    %% Creative Phase Selection
    IdentifyPhases --> SelectPhase["Select Next<br>Creative Phase"]
    SelectPhase --> PhaseType{"Creative<br>Phase Type?"}
    
    %% Creative Phase Types
    PhaseType -->|"UI/UX<br>Design"| UIPhase["UI/UX CREATIVE PHASE<br>Core/creative-phase-uiux.md (Conceptual)"]
    PhaseType -->|"Architecture<br>Design"| ArchPhase["ARCHITECTURE CREATIVE PHASE<br>Phases/CreativePhase/creative-phase-architecture.mdc"]
    PhaseType -->|"Data Model<br>Design"| DataPhase["DATA MODEL CREATIVE PHASE<br>Core/creative-phase-data.md (Conceptual)"]
    PhaseType -->|"Algorithm<br>Design"| AlgoPhase["ALGORITHM CREATIVE PHASE<br>Core/creative-phase-algorithm.md (Conceptual)"]
    
    %% UI/UX Creative Phase (Conceptual for brevity, actual rule would be loaded)
    UIPhase --> UI_Problem["Define UI/UX<br>Problem"]
    UI_Problem --> UI_Research["Research UI<br>Patterns"]
    UI_Research --> UI_Options["Explore UI<br>Options"]
    UI_Options --> UI_Evaluate["Evaluate User<br>Experience"]
    UI_Evaluate --> UI_Decision["Make Design<br>Decision"]
    UI_Decision --> UI_Document["Document UI<br>Design"]
    
    %% Architecture Creative Phase (Actual rule, see creative-phase-architecture.mdc)
    ArchPhase --> Arch_Problem["Define Architecture<br>Challenge"]
    Arch_Problem --> Arch_Options["Explore Architecture<br>Options"]
    Arch_Options --> Arch_Analyze["Analyze Tradeoffs"]
    Arch_Analyze --> Arch_Decision["Make Architecture<br>Decision"]
    Arch_Decision --> Arch_Document["Document<br>Architecture"]
    Arch_Document --> Arch_Diagram["Create Architecture<br>Diagram"]
    
    %% Data Model Creative Phase (Conceptual for brevity, actual rule would be loaded)
    DataPhase --> Data_Requirements["Define Data<br>Requirements"]
    Data_Requirements --> Data_Structure["Design Data<br>Structure"]
    Data_Structure --> Data_Relations["Define<br>Relationships"]
    Data_Relations --> Data_Validation["Design<br>Validation"]
    Data_Validation --> Data_Document["Document<br>Data Model"]
    
    %% Algorithm Creative Phase (Conceptual for brevity, actual rule would be loaded)
    AlgoPhase --> Algo_Problem["Define Algorithm<br>Problem"]
    Algo_Problem --> Algo_Options["Explore Algorithm<br>Approaches"]
    Algo_Options --> Algo_Evaluate["Evaluate Time/Space<br>Complexity"]
    Algo_Evaluate --> Algo_Decision["Make Algorithm<br>Decision"]
    Algo_Decision --> Algo_Document["Document<br>Algorithm"]
    
    %% Documentation & Completion
    UI_Document & Arch_Diagram & Data_Document & Algo_Document --> CreateDoc["Create Creative<br>Phase Document"]
    CreateDoc --> UpdateTasks["Update tasks.md<br>with Decision"]
    UpdateTasks --> MorePhases{"More Creative<br>Phases?"}
    MorePhases -->|"Yes"| SelectPhase
    MorePhases -->|"No"| VerifyComplete["Verify All<br>Phases Complete"]
    VerifyComplete --> NotifyComplete["Signal Creative<br>Phases Complete"]
```

## 📋 CREATIVE PHASE DOCUMENT FORMAT

Each creative phase should produce a document using the `optimized-creative-template.mdc` structure:

```mermaid
graph TD
    subgraph "Creative Phase Document"
        Header["🎨 CREATIVE PHASE: [TYPE]"]
        Problem["PROBLEM STATEMENT<br>Clear definition of the problem"]
        Options["OPTIONS ANALYSIS<br>Multiple approaches considered"]
        Pros["PROS & CONS<br>Tradeoffs for each option"]
        Decision["DECISION<br>Selected approach + rationale"]
        Impl["IMPLEMENTATION PLAN<br>Steps to implement the decision"]
        Diagram["VISUALIZATION<br>Diagrams of the solution"]
    end
    
    Header --> Problem --> Options --> Pros --> Decision --> Impl --> Diagram
```

## 🔍 CREATIVE TYPES AND APPROACHES

```mermaid
graph TD
    subgraph "UI/UX Design"
        UI1["User Flow<br>Analysis"]
        UI2["Component<br>Hierarchy"]
        UI3["Interaction<br>Patterns"]
        UI4["Visual Design<br>Principles"]
    end
    
    subgraph "Architecture Design"
        A1["Component<br>Structure"]
        A2["Data Flow<br>Patterns"]
        A3["Interface<br>Design"]
        A4["System<br>Integration"]
    end
    
    subgraph "Data Model Design"
        D1["Entity<br>Relationships"]
        D2["Schema<br>Design"]
        D3["Validation<br>Rules"]
        D4["Query<br>Optimization"]
    end
    
    subgraph "Algorithm Design"
        AL1["Complexity<br>Analysis"]
        AL2["Efficiency<br>Optimization"]
        AL3["Edge Case<br>Handling"]
        AL4["Scaling<br>Considerations"]
    end
```

## 📊 REQUIRED FILE STATE VERIFICATION

Before creative phase work can begin, verify file state:

```mermaid
graph TD
    Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>planning complete?"}
    
    CheckTasks -->|"No"| ErrorPlan["ERROR:<br>Return to PLAN Mode"]
    CheckTasks -->|"Yes"| CheckCreative{"Creative phases<br>identified?"}
    
    CheckCreative -->|"No"| ErrorCreative["ERROR:<br>Return to PLAN Mode"]
    CheckCreative -->|"Yes"| ReadyCreative["Ready for<br>Creative Phase"]
```

## 📋 OPTIONS ANALYSIS TEMPLATE REFERENCE

**Instructions:** For detailed options analysis, refer to the template structure in `Phases/CreativePhase/optimized-creative-template.mdc`.

## 🎨 CREATIVE PHASE MARKERS

Use these visual markers for creative phases:

```
🎨🎨🎨 ENTERING CREATIVE PHASE: [TYPE] 🎨🎨🎨

[Creative phase content]

🎨 CREATIVE CHECKPOINT: [Milestone]

[Additional content]

🎨🎨🎨 EXITING CREATIVE PHASE - DECISION MADE 🎨🎨🎨
```

## 📊 CREATIVE PHASE VERIFICATION CHECKLIST

```
✓ CREATIVE PHASE VERIFICATION
- Problem clearly defined? [YES/NO]
- Multiple options considered (3+)? [YES/NO]
- Pros/cons documented for each option? [YES/NO]
- Decision made with clear rationale? [YES/NO]
- Implementation plan included? [YES/NO]
- Visualization/diagrams created? [YES/NO]
- tasks.md updated with decision? [YES/NO]

→ If all YES: Creative phase complete
→ If any NO: Complete missing elements
```

## 🔄 MODE TRANSITION NOTIFICATION

When all creative phases are complete, notify user with:

```
## CREATIVE PHASES COMPLETE

✅ All required design decisions made
✅ Creative phase documents created
✅ tasks.md updated with decisions
✅ Implementation plan updated

→ NEXT RECOMMENDED MODE: IMPLEMENT MODE
```
```

---

**/isolation_rules/visual-maps/implement-mode-map.mdc:**
```markdown
---
description: Visual process map for IMPLEMENT mode (Code Implementation)
globs: "**/implement*/**", "**/code*/**", "**/build*/**"
alwaysApply: false
---

# IMPLEMENT MODE: CODE IMPLEMENTATION PROCESS MAP

> **TL;DR:** This visual map guides the IMPLEMENT mode, focusing on systematic code implementation, adherence to design decisions, and continuous testing based on the task's complexity level.

## 🧭 IMPLEMENT MODE PROCESS FLOW

```mermaid
graph TD
    Start["START IMPLEMENT MODE"] --> ReadTasks["Read tasks.md<br>and creative documents"]
    
    %% Initial Assessment
    ReadTasks --> VerifyDesign{"Design Decisions<br>Complete?"}
    VerifyDesign -->|"No"| ReturnCreative["Return to<br>CREATIVE Mode"]
    VerifyDesign -->|"Yes"| AssessLevel{"Determine<br>Complexity Level"}
    
    %% Level-Based Implementation
    AssessLevel -->|"Level 1"| L1Implement["LEVEL 1 IMPLEMENTATION<br>Level1/optimized-workflow-level1.mdc"]
    AssessLevel -->|"Level 2"| L2Implement["LEVEL 2 IMPLEMENTATION<br>Level2/workflow-level2.mdc"]
    AssessLevel -->|"Level 3"| L3Implement["LEVEL 3 IMPLEMENTATION<br>Level3/implementation-intermediate.mdc"]
    AssessLevel -->|"Level 4"| L4Implement["LEVEL 4 IMPLEMENTATION<br>Level4/phased-implementation.mdc (Conceptual)"]
    
    %% Level 1 Implementation (Quick Fix)
    L1Implement --> L1Code["Implement Fix<br>Quickly"]
    L1Code --> L1Test["Perform Minimal<br>Test"]
    L1Test --> L1Doc["Update tasks.md<br>with Solution"]
    
    %% Level 2 Implementation (Simple Enhancement)
    L2Implement --> L2Code["Implement Enhancement<br>Modularly"]
    L2Code --> L2Unit["Write Unit Tests"]
    L2Unit --> L2Integration["Perform Integration<br>Tests"]
    L2Integration --> L2Doc["Update tasks.md<br>& progress.md"]
    
    %% Level 3-4 Implementation (Intermediate Feature / Complex System)
    L3Implement & L4Implement --> L34Code["Implement Features<br>Iteratively"]
    L34Code --> L34Unit["Write Unit &<br>Component Tests"]
    L34Unit --> L34Integration["Perform Integration<br>Tests"]
    L34Integration --> L34E2E["Perform End-to-End<br>Tests"]
    L34E2E --> L34Review["Conduct Self-Review<br>& Linting"]
    L34Review --> L34Doc["Update tasks.md<br>progress.md & Code Comments"]
    
    %% Completion & Transition
    L1Doc & L2Doc & L34Doc --> VerifyComplete["Verify All<br>Implementation Complete"]
    VerifyComplete --> NotifyComplete["Signal Implementation<br>Complete"]
    NotifyComplete --> Transition["NEXT MODE:<br>REFLECT Mode (or QA if not done)"]
```

## 📋 IMPLEMENTATION GUIDELINES BY COMPLEXITY

```mermaid
graph TD
    subgraph "Level 1: Quick Fix"
        L1_1["Direct Code<br>Modification"]
        L1_2["Focus on Single<br>Component"]
        L1_3["Quick Local Test"]
    end
    
    subgraph "Level 2: Simple Enhancement"
        L2_1["Modular Component<br>Development"]
        L2_2["Basic Unit Testing"]
        L2_3["Integration with<br>Directly Affected Area"]
    end
    
    subgraph "Level 3: Intermediate Feature"
        L3_1["Iterative Development<br>by Sub-feature"]
        L3_2["Comprehensive Unit &<br>Component Testing"]
        L3_3["Dedicated Integration<br>Testing Phase"]
        L3_4["Adherence to Creative<br>Design Documents"]
    end
    
    subgraph "Level 4: Complex System"
        L4_1["Phased Implementation<br>by Subsystem"]
        L4_2["Rigorous Testing<br>Across Layers"]
        L4_3["Extensive Integration<br>with Existing Systems"]
        L4_4["Strict Governance &<br>Review Process"]
    end
    
    L1_1 --> L1_2 --> L1_3
    L2_1 --> L2_2 --> L2_3
    L3_1 --> L3_2 --> L3_3 --> L3_4
    L4_1 --> L4_2 --> L4_3 --> L4_4
```

## 📊 REQUIRED FILE STATE VERIFICATION

Before implementation can begin, verify file state:

```mermaid
graph TD
    Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>planning complete?"}
    
    CheckTasks -->|"No"| ErrorPlan["ERROR:<br>Return to PLAN Mode"]
    CheckTasks -->|"Yes"| CheckCreative{"Creative phases<br>identified & complete<br> (if required)?"}
    
    CheckCreative -->|"No"| ErrorCreative["ERROR:<br>Return to CREATIVE Mode"]
    CheckCreative -->|"Yes"| ReadyImplement["Ready for<br>Implementation"]
```

## 📝 PROGRESS DOCUMENTATION GUIDELINES

*   **`tasks.md`**: Update specific subtasks (`[ ]` to `[x]`) as completed.
*   **`progress.md`**: Add brief entries for significant milestones, completed modules, or resolved blockers.
*   **Code Comments**: Use for internal code explanations, especially for complex algorithms or design patterns.

## 📋 IMPLEMENTATION VERIFICATION CHECKLIST

```
✓ IMPLEMENTATION VERIFICATION
- All subtasks for current phase completed? [YES/NO]
- Code changes aligned with plan/design? [YES/NO]
- Necessary tests written and passed? [YES/NO]
- tasks.md updated with progress? [YES/NO]
- progress.md updated (if significant)? [YES/NO]
- Code reviewed (self-review/linting)? [YES/NO]

→ If all YES: Implementation phase for this segment complete
→ If any NO: Complete missing elements or address issues
```

## 🔄 MODE TRANSITION NOTIFICATION

When all implementation phases for the task are complete:

```
## IMPLEMENTATION COMPLETE

✅ All planned features/fixes implemented
✅ Code tested and reviewed
✅ tasks.md and progress.md updated
✅ Final verification passed

→ NEXT RECOMMENDED MODE: REFLECT MODE
```
```

---

**/isolation_rules/visual-maps/plan-mode-map.mdc:**
```markdown
---
description: Visual process map for PLAN mode (Code Implementation)
globs: plan-mode-map.mdc
alwaysApply: false
---

# PLAN MODE: TASK PLANNING PROCESS MAP

> **TL;DR:** This visual map guides the PLAN mode process, focusing on creating detailed implementation plans based on the complexity level determined during initialization, with mandatory technology validation before implementation.

## 🧭 PLAN MODE PROCESS FLOW

```mermaid
graph TD
    Start["START PLANNING"] --> ReadTasks["Read tasks.md"]
    
    %% Complexity Level Determination
    ReadTasks --> CheckLevel{"Determine<br>Complexity Level"}
    CheckLevel -->|"Level 2"| Level2["LEVEL 2 PLANNING<br>Level2/workflow-level2.mdc"]
    CheckLevel -->|"Level 3"| Level3["LEVEL 3 PLANNING<br>Level3/planning-comprehensive.mdc"]
    CheckLevel -->|"Level 4"| Level4["LEVEL 4 PLANNING<br>Level4/planning-comprehensive.mdc (Conceptual)"]
    
    %% Planning Steps (details loaded from level-specific rules)
    Level2 --> L2PlanSummary["Follow Level 2 Workflow Steps 3-6"]
    Level3 --> L3PlanSummary["Follow Level 3 Planning Comprehensive"]
    Level4 --> L4PlanSummary["Follow Level 4 Planning Comprehensive"]
    
    L2PlanSummary & L3PlanSummary & L4PlanSummary --> L_MCP_Research["**TECHNOLOGY RESEARCH (MCP)**<br>Use MCP to investigate new libraries/frameworks"]
    L_MCP_Research --> L_MCP_Workflow["**MCP Workflow**:<br>1. `read_wiki_structure` for overview<br>2. `ask_question` for architecture/use-cases<br>3. `read_wiki_contents` for tutorials<br>4. Update techContext.md with findings"]
    
    %% Technology Validation Gate
    L_MCP_Workflow --> TechGate["⛔ TECHNOLOGY<br>VALIDATION GATE"]
    TechGate --> TechSelection["Document Technology<br>Stack Selection"]
    TechSelection --> TechHelloWorld["Create Hello World<br>Proof of Concept"]
    TechHelloWorld --> TechDependencies["Verify Required<br>Dependencies"]
    TechDependencies --> TechConfig["Validate Build<br>Configuration"]
    TechConfig --> TechBuild["Complete Test<br>Build"]
    TechBuild --> TechVerify["⛔ TECHNOLOGY<br>CHECKPOINT"]
    
    %% Verification & Completion
    TechVerify --> PlanCompletion{"Plan Completeness<br>Verified?"}
    
    PlanCompletion --> L3Flag["Flag Components<br>Requiring Creative"]
    PlanCompletion --> L4Flag["Flag Components<br>Requiring Creative"]
 
    L3Flag & L4Flag & PlanCompletion --> CheckCreative{"Creative<br>Phases<br>Required?"}
    
    %% Mode Transition
    CheckCreative -->|"Yes"| RecCreative["NEXT MODE:<br>CREATIVE MODE"]
    CheckCreative -->|"No"| RecImplement["NEXT MODE:<br>IMPLEMENT MODE"]
```

## 📋 LEVEL-SPECIFIC PLANNING APPROACHES

```mermaid
graph TD
    subgraph "Level 2: Enhancement"
        L2A["Basic Requirements<br>Analysis"]
        L2B["Simple Component<br>Identification"]
        L2C["Linear Implementation<br>Plan"]
        L2D["Basic Checklist<br>Creation"]
    end
    
    subgraph "Level 3: Feature"
        L3A["Detailed Requirements<br>Analysis"]
        L3B["Component Mapping<br>with Dependencies"]
        L3C["Multi-Phase<br>Implementation Plan"]
        L3D["Comprehensive<br>Checklist"]
        L3E["Creative Phase<br>Identification"]
    end
    
    subgraph "Level 4: System (Conceptual for brevity)"
        L4A["Architectural<br>Requirements Analysis"]
        L4B["System Component<br>Mapping"]
        L4C["Subsystem<br>Integration Plan"]
        L4D["Phased Implementation<br>Strategy"]
        L4E["Risk Assessment<br>& Mitigation"]
        L4F["Multiple Creative<br>Phase Requirements"]
    end
    
    L2A --> L2B --> L2C --> L2D
    L3A --> L3B --> L3C --> L3D --> L3E
    L4A --> L4B --> L4C --> L4D --> L4E --> L4F
```

## 🔧 TECHNOLOGY VALIDATION WORKFLOW

```mermaid
graph TD
    Start["Technology<br>Validation Start"] --> Select["Technology<br>Stack Selection"]
    Select --> Document["Document Chosen<br>Technologies"]
    Document --> POC["Create Minimal<br>Proof of Concept"]
    POC --> Build["Verify Build<br>Process Works"]
    Build --> Dependencies["Validate All<br>Dependencies"]
    Dependencies --> Config["Confirm Configuration<br>Files Are Correct"]
    Config --> Test["Complete Test<br>Build/Run"]
    Test --> Success{"All Checks<br>Pass?"}
    
    Success -->|"Yes"| Ready["Ready for<br>Implementation"]
    Success -->|"No"| Fix["Fix Technology<br>Issues"]
    Fix --> Document
```

## 📊 REQUIRED FILE STATE VERIFICATION

Before planning can begin, verify the file state:

```mermaid
graph TD
    Start["File State<br>Verification"] --> CheckTasks{"tasks.md<br>initialized?"}
    
    CheckTasks -->|"No"| ErrorTasks["ERROR:<br>Return to VAN Mode"]
    CheckTasks -->|"Yes"| CheckActive{"activeContext.md<br>exists?"}
    
    CheckActive -->|"No"| ErrorActive["ERROR:<br>Return to VAN Mode"]
    CheckActive -->|"Yes"| ReadyPlan["Ready for<br>Planning"]
```

## 📝 TASKS.MD UPDATE FORMAT (DURING PLANNING)

During planning, update `tasks.md` with this structure:

```
# Task: [Task name]

## Description
[Detailed description]

## Complexity
Level: [2/3/4]
Type: [Enhancement/Feature/Complex System]

## Technology Stack
- Framework: [Selected framework]
- Build Tool: [Selected build tool]
- Language: [Selected language]
- Storage: [Selected storage mechanism]

## Technology Validation Checkpoints
- [ ] Project initialization command verified
- [ ] Required dependencies identified and installed
- [ ] Build configuration validated
- [ ] Hello world verification completed
- [ ] Test build passes successfully

## Status
- [x] Initialization complete
- [x] Planning complete
- [ ] Technology validation complete
- [ ] [Implementation steps]

## Implementation Plan
1. [Step 1]
   - [Subtask 1.1]
   - [Subtask 1.2]
2. [Step 2]
   - [Subtask 2.1]
   - [Subtask 2.2]

## Creative Phases Required
- [ ] [Component 1] Design
- [ ] [Component 2] Architecture
- [ ] [Component 3] Data Model

## Dependencies
- [Dependency 1]
- [Dependency 2]

## Challenges & Mitigations
- [Challenge 1]: [Mitigation strategy]
- [Challenge 2]: [Mitigation strategy]
```

## 📋 CREATIVE PHASE IDENTIFICATION

For Level 3-4 tasks, identify components requiring creative phases:

```mermaid
graph TD
    Start["Creative Phase<br>Identification"] --> CheckComp{"Component<br>Analysis"}
    
    CheckComp --> UI["UI/UX<br>Components"]
    CheckComp --> Data["Data Model<br>Components"]
    CheckComp --> Arch["Architecture<br>Components"]
    CheckComp --> Algo["Algorithm<br>Components"]
    
    UI & Data & Arch & Algo --> Decision{"Design Decisions<br>Required?"}
    
    Decision -->|"Yes"| Flag["Flag for<br>Creative Phase"]
    Decision -->|"No"| Skip["Standard<br>Implementation"]
    
    Flag --> Document["Document in<br>tasks.md"]
```

## 📊 TECHNOLOGY VALIDATION CHECKLIST

```
✓ TECHNOLOGY VALIDATION CHECKLIST
- Technology stack clearly defined? [YES/NO]
- Project initialization command documented? [YES/NO]
- Required dependencies identified? [YES/NO]
- Minimal proof of concept created? [YES/NO]
- Hello world build/run successful? [YES/NO]
- Configuration files validated? [YES/NO]
- Test build completes successfully? [YES/NO]

→ If all YES: Technology validation complete - ready for next phase
→ If any NO: Resolve technology issues before proceeding
```

## 📊 PLAN VERIFICATION CHECKLIST

```
✓ PLAN VERIFICATION CHECKLIST
- Requirements clearly documented? [YES/NO]
- Technology stack validated? [YES/NO]
- Affected components identified? [YES/NO]
- Implementation steps detailed? [YES/NO]
- Dependencies documented? [YES/NO]
- Challenges & mitigations addressed? [YES/NO]
- Creative phases identified (Level 3-4)? [YES/NO/NA]
- tasks.md updated with plan? [YES/NO]

→ If all YES: Planning complete - ready for next mode
→ If any NO: Complete missing plan elements
```

## 🔄 MODE TRANSITION NOTIFICATION

When planning is complete, notify user with:

```
## PLANNING COMPLETE

✅ Implementation plan created
✅ Technology stack validated
✅ tasks.md updated with plan
✅ Challenges and mitigations documented
[✅ Creative phases identified (for Level 3-4)]

→ NEXT RECOMMENDED MODE: [CREATIVE/IMPLEMENT] MODE
```
```

---

**/isolation_rules/visual-maps/reflect-mode-map.mdc:**
```markdown
---
description: Visual process map for REFLECT mode (Task Reflection)
globs: "**/reflect*/**", "**/review*/**", "**/retrospect*/**"
alwaysApply: false
---

# REFLECT MODE: TASK REVIEW PROCESS MAP

> **TL;DR:** This visual map guides the REFLECT mode process, focusing on structured review of the implementation, documenting lessons learned, and preparing insights for future reference.

## 🧭 REFLECT MODE PROCESS FLOW

```mermaid
graph TD
    Start["START REFLECT MODE"] --> ReadTasks["Read tasks.md<br>and progress.md"]
    
    %% Initial Assessment
    ReadTasks --> VerifyImplement{"Implementation<br>Complete?"}
    VerifyImplement -->|"No"| ReturnImplement["Return to<br>IMPLEMENT Mode"]
    VerifyImplement -->|"Yes"| AssessLevel{"Determine<br>Complexity Level"}
    
    %% Level-Based Reflection
    AssessLevel -->|"Level 1"| L1Reflect["LEVEL 1 REFLECTION<br>Level1/optimized-workflow-level1.mdc (Conceptual)"]
    AssessLevel -->|"Level 2"| L2Reflect["LEVEL 2 REFLECTION<br>Level2/reflection-basic.mdc"]
    AssessLevel -->|"Level 3"| L3Reflect["LEVEL 3 REFLECTION<br>Level3/reflection-intermediate.mdc"]
    AssessLevel -->|"Level 4"| L4Reflect["LEVEL 4 REFLECTION<br>Level4/reflection-comprehensive.mdc (Conceptual)"]
    
    %% Level 1 Reflection (Quick) - Handled by Level 1 workflow's documentation phase
    L1Reflect --> L1Review["Review<br>Bug Fix"]
    L1Review --> L1Document["Document<br>Solution in tasks.md"]
    L1Document --> L1Update["Update<br>tasks.md"]
    
    %% Level 2 Reflection (Standard) - Handled by Level 2 workflow's reflection-basic.mdc
    L2Reflect --> L2Review["Review<br>Enhancement"]
    L2Review --> L2WWW["Document<br>What Went Well"]
    L2WWW --> L2Challenges["Document<br>Challenges"]
    L2Challenges --> L2Lessons["Document<br>Lessons Learned"]
    L2Lessons --> L2Update["Update<br>tasks.md"]
    
    %% Level 3-4 Reflection (Comprehensive) - Handled by Level 3 workflow's reflection-intermediate.mdc
    L3Reflect & L4Reflect --> L34Review["Review Implementation<br>& Creative Phases"]
    L34Review --> L34Plan["Compare Against<br>Original Plan"]
    L34Plan --> L34WWW["Document<br>What Went Well"]
    L34WWW --> L34Challenges["Document<br>Challenges"]
    L34Challenges --> L34Lessons["Document<br>Lessons Learned"]
    L34Lessons --> L34ImproveProcess["Document Process<br>Improvements"]
    L34ImproveProcess --> L34Update["Update<br>tasks.md"]
    
    %% Completion & Transition
    L1Update & L2Update & L34Update --> CreateReflection["Create<br>reflection.md (for L2-4)"]
    CreateReflection --> UpdateSystem["Update System<br>Documentation (if any)"]
    UpdateSystem --> Transition["NEXT MODE:<br>ARCHIVE MODE"]
```

## 📋 REFLECTION STRUCTURE

The reflection should follow this structured format (specifics vary by level, see individual level rules):

```mermaid
graph TD
    subgraph "Reflection Document Structure"
        Header["# TASK REFLECTION: [Task Name]"]
        Summary["## SUMMARY<br>Brief summary of completed task"]
        WWW["## WHAT WENT WELL<br>Successful aspects of implementation"]
        Challenges["## CHALLENGES<br>Difficulties encountered during implementation"]
        Lessons["## LESSONS LEARNED<br>Key insights gained from the experience"]
        ProcessImp["## PROCESS IMPROVEMENTS<br>How to improve for future tasks"]
        TechImp["## TECHNICAL IMPROVEMENTS<br>Better approaches for similar tasks"]
        NextSteps["## NEXT STEPS<br>Follow-up actions or future work"]
    end
    
    Header --> Summary --> WWW --> Challenges --> Lessons --> ProcessImp --> TechImp --> NextSteps
```

## 📊 REQUIRED FILE STATE VERIFICATION

Before reflection can begin, verify file state:

```mermaid
graph TD
    Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>implementation<br>complete?"}
    
    CheckTasks -->|"No"| ErrorImplement["ERROR:<br>Return to IMPLEMENT Mode"]
    CheckTasks -->|"Yes"| CheckProgress{"progress.md<br>has implementation<br>details?"}
    
    CheckProgress -->|"No"| ErrorProgress["ERROR:<br>Update progress.md first"]
    CheckProgress -->|"Yes"| ReadyReflect["Ready for<br>Reflection"]
```

## 🔍 IMPLEMENTATION REVIEW APPROACH

```mermaid
graph TD
    subgraph "Implementation Review"
        Original["Review Original<br>Requirements"]
        Plan["Compare Against<br>Implementation Plan"]
        Actual["Assess Actual<br>Implementation"]
        Creative["Review Creative<br>Phase Decisions"]
        Changes["Identify Deviations<br>from Plan"]
        Results["Evaluate<br>Results"]
    end
    
    Original --> Plan --> Actual
    Plan --> Creative --> Changes
    Actual --> Results
    Changes --> Results
```

## 📝 REFLECTION DOCUMENT TEMPLATES

### Level 1 (Basic) Reflection (Integrated into tasks.md)
```markdown
# Bug Fix Reflection: [Bug Name] (within tasks.md)

## Summary
[Brief description of the bug and solution]

## Implementation
[Description of the fix implemented]

## Testing
[Description of testing performed]

## Additional Notes
[Any other relevant information]
```

### Levels 2 (Basic) Reflection (See `Level2/reflection-basic.mdc`)
### Levels 3-4 (Comprehensive) Reflection (See `Level3/reflection-intermediate.mdc` or equivalent Level 4)

## 📊 REFLECTION QUALITY METRICS

```mermaid
graph TD
    subgraph "Reflection Quality Metrics"
        Specific["Specific<br>Not general or vague"]
        Actionable["Actionable<br>Provides clear direction"]
        Honest["Honest<br>Acknowledges successes and failures"]
        Forward["Forward-Looking<br>Focuses on future improvement"]
        Evidence["Evidence-Based<br>Based on concrete examples"]
    end
```

## 📋 TASKS.MD UPDATE FORMAT

During reflection, update `tasks.md` with:

```
## Status
- [x] Initialization complete
- [x] Planning complete
[For Level 3-4:]
- [x] Creative phases complete
- [x] Implementation complete
- [x] Reflection complete
- [ ] Archiving

## Reflection Highlights
- **What Went Well**: [Key successes]
- **Challenges**: [Key challenges]
- **Lessons Learned**: [Key lessons]
- **Next Steps**: [Follow-up actions]
```

## 📊 REFLECTION VERIFICATION CHECKLIST

```
✓ REFLECTION VERIFICATION
- Implementation thoroughly reviewed? [YES/NO]
- What Went Well section completed? [YES/NO]
- Challenges section completed? [YES/NO]
- Lessons Learned section completed? [YES/NO]
- Process Improvements identified? [YES/NO]
- Technical Improvements identified? [YES/NO]
- Next Steps documented? [YES/NO]
- reflection.md created (for L2+)? [YES/NO]
- tasks.md updated with reflection status? [YES/NO]

→ If all YES: Reflection complete - ready for ARCHIVE mode
→ If any NO: Complete missing reflection elements
```

## 🔄 MODE TRANSITION NOTIFICATION

When reflection is complete, notify user with:

```
## REFLECTION COMPLETE

✅ Implementation thoroughly reviewed
✅ Reflection document created
✅ Lessons learned documented
✅ Process improvements identified
✅ tasks.md updated with reflection status

→ NEXT RECOMMENDED MODE: ARCHIVE MODE
```
```

---

**/isolation_rules/visual-maps/van_mode_split/van-complexity-determination.mdc:**
```markdown
---
description: Visual process map for VAN mode complexity determination
globs: van-complexity-determination.mdc
alwaysApply: false
---
# VAN MODE: COMPLEXITY DETERMINATION

> **TL;DR:** This component determines the appropriate complexity level (1-4) for the current task and directs the workflow accordingly.

## 🔍 COMPLEXITY DECISION TREE

```mermaid
graph TD
    Start["New Task"] --> Q1{"Bug fix or<br>error correction?"}
    Q1 -->|Yes| Q1a{"Affects single<br>component?"}
    Q1a -->|Yes| L1["Level 1:<br>Quick Bug Fix"]
    Q1a -->|No| Q1b{"Affects multiple<br>components?"}
    Q1b -->|Yes| L2["Level 2:<br>Simple Enhancement"]
    Q1b -->|No| Q1c{"Affects system<br>architecture?"}
    Q1c -->|Yes| L3["Level 3:<br>Intermediate Feature"]
    Q1c -->|No| L2
    
    Q1 -->|No| Q2{"Adding small<br>feature or<br>enhancement?"}
    Q2 -->|Yes| Q2a{"Self-contained<br>change?"}
    Q2a -->|Yes| L2
    Q2a -->|No| Q2b{"Affects multiple<br>components?"}
    Q2b -->|Yes| L3
    Q2b -->|No| L2
    
    Q2 -->|No| Q3{"Complete feature<br>requiring multiple<br>components?"}
    Q3 -->|Yes| Q3a{"Architectural<br>implications?"}
    Q3a -->|Yes| L4["Level 4:<br>Complex System"]
    Q3a -->|No| L3
    
    Q3 -->|No| Q4{"System-wide or<br>architectural<br>change?"}
    Q4 -->|Yes| L4
    Q4 -->|No| L3
```

## 📋 LEVEL INDICATORS

### Level 1: Quick Bug Fix
- **Keywords**: fix, bug, error, crash, issue
- **Scope**: Single component
- **Time**: Minutes to hours
- **Risk**: Low, isolated
- **Example**: Button not working, styling issue

### Level 2: Simple Enhancement
- **Keywords**: add, improve, update, enhance
- **Scope**: Single component/subsystem
- **Time**: Hours to 1-2 days
- **Risk**: Moderate, contained
- **Example**: Add form field, improve validation

### Level 3: Intermediate Feature
- **Keywords**: implement, create, develop
- **Scope**: Multiple components
- **Time**: Days to 1-2 weeks
- **Risk**: Significant
- **Example**: User authentication, dashboard

### Level 4: Complex System
- **Keywords**: system, architecture, redesign
- **Scope**: Multiple subsystems
- **Time**: Weeks to months
- **Risk**: High, architectural
- **Example**: Payment system, microservices

## 📋 COMPLEXITY CHECKLIST

```
✓ COMPLEXITY DETERMINATION
- Task type identified? [YES/NO]
- Scope assessed? [YES/NO]
- Time estimated? [YES/NO]
- Risk evaluated? [YES/NO]
- Dependencies mapped? [YES/NO]

→ If all YES: Proceed with level-specific workflow
→ If any NO: Complete assessment
```

## 🔄 LEVEL TRANSITION TRIGGERS

```mermaid
graph TD
    Current["Current Level"] --> Higher["Level Up Triggers"]
    Current --> Lower["Level Down Triggers"]
    
    Higher --> H1["Multiple Components"]
    Higher --> H2["Design Decisions"]
    Higher --> H3["System Impact"]
    
    Lower --> L1["Isolated Change"]
    Lower --> L2["Simple Fix"]
    Lower --> L3["No Design Needed"]
```

## 📋 WORKFLOW LOADING

Based on determined level:
- Level 1: Continue in VAN mode (e.g., to `optimized-workflow-level1.mdc`)
- Level 2-4: Transition to PLAN mode

**Next Step:** Load appropriate level-specific workflow.

## 🚨 MODE TRANSITION TRIGGER (VAN to PLAN)

If complexity is determined to be Level 2, 3, or 4:

```
🚫 LEVEL [2-4] TASK DETECTED
Implementation in VAN mode is BLOCKED
This task REQUIRES PLAN mode
You MUST switch to PLAN mode for proper documentation and planning
Type 'PLAN' to switch to planning mode
```

## 📋 CHECKPOINT VERIFICATION TEMPLATE (Example)

```
✓ SECTION CHECKPOINT: COMPLEXITY DETERMINATION
- Task Analyzed? [YES/NO]
- Complexity Level Determined? [YES/NO]

→ If Level 1: Proceed to VAN Mode Completion.
→ If Level 2-4: Trigger PLAN Mode transition.
```
```

---

**/isolation_rules/visual-maps/van_mode_split/van-platform-detection.mdc:**
```markdown
---
description: Visual process map for VAN mode platform detection
globs: van-platform-detection.mdc
alwaysApply: false
---
# VAN MODE: PLATFORM DETECTION

> **TL;DR:** Detects the OS, determines path separators, and notes command adaptations required.

## 🌐 PLATFORM DETECTION PROCESS

```mermaid
graph TD
    PD["Platform Detection"] --> CheckOS["Detect Operating System"]
    CheckOS --> Win["Windows"]
    CheckOS --> Mac["macOS"]
    CheckOS --> Lin["Linux"]
    
    Win & Mac & Lin --> Adapt["Adapt Commands<br>for Platform"]
    
    Win --> WinPath["Path: Backslash (\\)"]
    Mac --> MacPath["Path: Forward Slash (/)"]
    Lin --> LinPath["Path: Forward Slash (/)"]
    
    Win --> WinCmd["Command Adaptations:<br>dir, icacls, etc."]
    Mac --> MacCmd["Command Adaptations:<br>ls, chmod, etc."]
    Lin --> LinCmd["Command Adaptations:<br>ls, chmod, etc."]
    
    WinPath & MacPath & LinPath --> PathCP["Path Separator<br>Checkpoint"]
    WinCmd & MacCmd & LinCmd --> CmdCP["Command<br>Checkpoint"]
    
    PathCP & CmdCP --> PlatformComplete["Platform Detection<br>Complete"]
```

## 📋 CHECKPOINT VERIFICATION TEMPLATE (Example)

```
✓ SECTION CHECKPOINT: PLATFORM DETECTION
- Operating System Detected? [YES/NO]
- Path Separator Confirmed? [YES/NO]
- Command Adaptations Noted? [YES/NO]

→ If all YES: Platform Detection Complete.
→ If any NO: Resolve before proceeding.
```

**Next Step:** Load and process `isolation_rules/Core/file-verification.mdc`.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-checks/build-test.mdc:**
```markdown
---
description: Process map for VAN QA minimal build test
globs: van-qa-checks/build-test.mdc
alwaysApply: false
---
# VAN QA: MINIMAL BUILD TEST

> **TL;DR:** This component performs a minimal build test to ensure core build functionality works properly.

## 4️⃣ MINIMAL BUILD TEST PROCESS

```mermaid
graph TD
    Start["Minimal Build Test"] --> CreateTest["Create Minimal<br>Test Project"]
    CreateTest --> BuildTest["Attempt<br>Build"]
    BuildTest --> BuildStatus{"Build<br>Successful?"}
    
    BuildStatus -->|"Yes"| RunTest["Run Basic<br>Functionality Test"]
    BuildStatus -->|"No"| FixBuild["Fix Build<br>Issues"]
    FixBuild --> RetryBuild["Retry Build"]
    RetryBuild --> BuildStatus
    
    RunTest --> TestStatus{"Test<br>Passed?"}
    TestStatus -->|"Yes"| TestSuccess["Minimal Build Test<br>✅ PASS"]
    TestStatus -->|"No"| FixTest["Fix Test<br>Issues"]
    FixTest --> RetryTest["Retry Test"]
    RetryTest --> TestStatus
```

### Minimal Build Test Commands (Examples for guidance, adapt for project/OS):
```bash
# Example: Perform minimal build test for a React project (Unix-like)
# Create a temporary directory for the test
mkdir .__build_test
cd .__build_test

# Initialize a minimal package.json
echo '{ "name": "build-test", "version": "1.0.0", "scripts": { "build": "echo Build test successful && exit 0" } }' > package.json

# Attempt build (uses the simple script defined above)
npm run build

# Check build success (npm run build exits with 0 on success)
if [ $? -eq 0 ]; then
    echo "Build process successful."
    # Create minimal test file
    echo "console.log('Test successful');" > index.js
    
    # Run basic test
    node index.js
    
    if [ $? -eq 0 ]; then
        echo "✅ Minimal build test passed successfully"
        exit 0
    else
        echo "❌ Basic functionality test failed"
        exit 1
    fi
else
    echo "❌ Build process failed"
    exit 1
fi

# Cleanup (Run this regardless of success/failure)
cd ..
rm -rf .__build_test
```

### Minimal Build Test Commands (Examples for guidance, adapt for project/OS):
```powershell
# Example: Perform minimal build test for a React project (PowerShell)
$testDir = ".__build_test"
if (Test-Path $testDir) { Remove-Item -Path $testDir -Recurse -Force }

try {
    New-Item -Path $testDir -ItemType Directory | Out-Null
    Push-Location $testDir
    
    @"
{
  "name": "build-test",
  "version": "1.0.0",
  "scripts": {
    "build": "echo Build test successful"
  }
}
"@ | Set-Content -Path "package.json"
    
    npm run build | Out-Null
    if ($LASTEXITCODE -eq 0) {
        Write-Output "Build process successful."
        @"
console.log('Test successful');
"@ | Set-Content -Path "index.js"
        
        node index.js | Out-Null
        if ($LASTEXITCODE -eq 0) {
            Write-Output "✅ Minimal build test passed successfully"
        } else {
            Write-Output "❌ Basic functionality test failed"
        }
    } else {
        Write-Output "❌ Build process failed"
    }
} catch {
    Write-Output "❌ Build test failed: $($_.Exception.Message)"
} finally {
    Pop-Location
    if (Test-Path $testDir) { Remove-Item -Path $testDir -Recurse -Force }
}
```

## 📋 MINIMAL BUILD TEST CHECKPOINT

```
✓ CHECKPOINT: MINIMAL BUILD TEST
- Test project creation successful? [YES/NO]
- Build process completed successfully? [YES/NO]
- Basic functionality test passed? [YES/NO]

→ If all YES: QA Validation complete, proceed to generate success report.
→ If any NO: Fix build issues before continuing.
```

**Next Step (on PASS):** Load `van-qa-utils/reports.mdc` to generate success report.
**Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for build test fixes.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-checks/config-check.mdc:**
```markdown
---
description: Process map for VAN QA configuration validation
globs: van-qa-checks/config-check.mdc
alwaysApply: false
---
# VAN QA: CONFIGURATION VALIDATION

> **TL;DR:** This component validates configuration files for proper syntax and compatibility with the project and platform.

## 2️⃣ CONFIGURATION VALIDATION PROCESS

```mermaid
graph TD
    Start["Configuration Validation"] --> IdentifyConfigs["Identify Configuration<br>Files"]
    IdentifyConfigs --> ReadConfigs["Read Configuration<br>Files"]
    ReadConfigs --> ValidateSyntax["Validate Syntax<br>and Format"]
    ValidateSyntax --> SyntaxStatus{"Syntax<br>Valid?"}
    
    SyntaxStatus -->|"Yes"| CheckCompatibility["Check Compatibility<br>with Platform"]
    SyntaxStatus -->|"No"| FixSyntax["Fix Syntax<br>Errors"]
    FixSyntax --> RetryValidate["Retry Validation"]
    RetryValidate --> SyntaxStatus
    
    CheckCompatibility --> CompatStatus{"Compatible with<br>Platform?"}
    CompatStatus -->|"Yes"| ConfigSuccess["Configurations Validated<br>✅ PASS"]
    CompatStatus -->|"No"| AdaptConfigs["Adapt Configurations<br>for Platform"]
    AdaptConfigs --> RetryCompat["Retry Compatibility<br>Check"]
    RetryCompat --> CompatStatus
```

### Configuration Validation Commands (Examples for guidance, adapt for project/OS):
```bash
# Example: Validate configuration files for a web project (Unix-like)
CONFIG_FILES=("package.json" "tsconfig.json" "vite.config.js")
INVALID_CONFIGS=()
INCOMPATIBLE_CONFIGS=()

for config_file in "${CONFIG_FILES[@]}"; do
    if [ -f "$config_file" ]; then
        if [[ "$config_file" == *.json ]]; then
            # Validate JSON syntax
            jq . "$config_file" > /dev/null 2>&1
            if [ $? -ne 0 ]; then
                INVALID_CONFIGS+=("$config_file (JSON syntax error)")
                continue
            fi
        fi
        
        # Specific configuration compatibility checks (e.g., for Vite React project)
        if [[ "$config_file" == "vite.config.js" ]]; then
            if ! grep -q "react()" "$config_file"; then
                INCOMPATIBLE_CONFIGS+=("$config_file (Missing React plugin for React project)")
            fi
        fi
    else
        INVALID_CONFIGS+=("$config_file (file not found)")
    fi
done

if [ ${#INVALID_CONFIGS[@]} -eq 0 ] && [ ${#INCOMPATIBLE_CONFIGS[@]} -eq 0 ]; then
    echo "✅ All configurations validated and compatible"
    exit 0
else
    if [ ${#INVALID_CONFIGS[@]} -gt 0 ]; then
        echo "❌ Invalid configurations: ${INVALID_CONFIGS[*]}"
    fi
    if [ ${#INCOMPATIBLE_CONFIGS[@]} -gt 0 ]; then
        echo "❌ Incompatible configurations: ${INCOMPATIBLE_CONFIGS[*]}"
    fi
    exit 1
fi
```
```powershell
# Example: Validate configuration files for a web project (PowerShell)
$configFiles = @(
    "package.json",
    "tsconfig.json",
    "vite.config.js"
)

$invalidConfigs = @()
$incompatibleConfigs = @()

foreach ($configFile in $configFiles) {
    if (Test-Path $configFile) {
        if ($configFile -match "\.json$") {
            try {
                Get-Content $configFile -Raw | ConvertFrom-Json | Out-Null
            } catch {
                $invalidConfigs += "$configFile (JSON syntax error: $($_.Exception.Message))"
                continue
            }
        }
        
        if ($configFile -eq "vite.config.js") {
            $content = Get-Content $configFile -Raw
            if ($content -notmatch "react\(\)") {
                $incompatibleConfigs += "$configFile (Missing React plugin for React project)"
            }
        }
    } else {
        $invalidConfigs += "$configFile (file not found)"
    }
}

if ($invalidConfigs.Count -eq 0 -and $incompatibleConfigs.Count -eq 0) {
    Write-Output "✅ All configurations validated and compatible"
    exit 0
} else {
    if ($invalidConfigs.Count -gt 0) {
        Write-Output "❌ Invalid configurations: $($invalidConfigs -join ', ')"
    }
    if ($incompatibleConfigs.Count -gt 0) {
        Write-Output "❌ Incompatible configurations: $($incompatibleConfigs -join ', ')"
    }
    exit 1
}
```

## 📋 CONFIGURATION VALIDATION CHECKPOINT

```
✓ CHECKPOINT: CONFIGURATION VALIDATION
- All configuration files found? [YES/NO]
- All configuration syntax valid? [YES/NO]
- All configurations compatible with platform? [YES/NO]

→ If all YES: Continue to Environment Validation.
→ If any NO: Fix configuration issues before continuing.
```

**Next Step (on PASS):** Load `van-qa-checks/environment-check.mdc`.
**Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for configuration fixes.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-checks/dependency-check.mdc:**
```markdown
---
description: Process map for VAN QA dependency verification
globs: van-qa-checks/dependency-check.mdc
alwaysApply: false
---
# VAN QA: DEPENDENCY VERIFICATION

> **TL;DR:** This component verifies that all required dependencies are installed and compatible with the project requirements.

## 1️⃣ DEPENDENCY VERIFICATION PROCESS

```mermaid
graph TD
    Start["Dependency Verification"] --> ReadDeps["Read Required Dependencies<br>from Creative Phase"]
    ReadDeps --> CheckInstalled["Check if Dependencies<br>are Installed"]
    CheckInstalled --> DepStatus{"All Dependencies<br>Installed?"}
    
    DepStatus -->|"Yes"| VerifyVersions["Verify Versions<br>and Compatibility"]
    DepStatus -->|"No"| InstallMissing["Install Missing<br>Dependencies"]
    InstallMissing --> VerifyVersions
    
    VerifyVersions --> VersionStatus{"Versions<br>Compatible?"}
    VersionStatus -->|"Yes"| DepSuccess["Dependencies Verified<br>✅ PASS"]
    VersionStatus -->|"No"| UpgradeVersions["Upgrade/Downgrade<br>as Needed"]
    UpgradeVersions --> RetryVerify["Retry Verification"]
    RetryVerify --> VersionStatus
```

### Dependency Verification Commands (Examples for guidance, adapt for project/OS):
```bash
# Example: Verify Node.js dependencies for a React project (Unix-like)
verify_dependencies() {
    local missing_deps=()
    local incompatible_deps=()
    
    # Check Node.js version
    if command -v node &> /dev/null; then
        local node_version=$(node -v)
        if [[ $node_version =~ v([0-9]+)\.([0-9]+)\.([0-9]+) ]]; then
            local major=${BASH_REMATCH[1]}
            if (( major < 14 )); then
                incompatible_deps+=("node (found $node_version, required >=14.0.0)")
            fi
        fi
    else
        missing_deps+=("node")
    fi
    
    # Check npm version
    if command -v npm &> /dev/null; then
        local npm_version=$(npm -v)
        if [[ $npm_version =~ ([0-9]+)\.([0-9]+)\.([0-9]+) ]]; then
            local major=${BASH_REMATCH[1]}
            if (( major < 6 )); then
                incompatible_deps+=("npm (found $npm_version, required >=6.0.0)")
            fi
        fi
    else
        missing_deps+=("npm")
    fi
    
    if [ ${#missing_deps[@]} -eq 0 ] && [ ${#incompatible_deps[@]} -eq 0 ]; then
        echo "✅ All dependencies verified and compatible"
        return 0
    else
        if [ ${#missing_deps[@]} -gt 0 ]; then
            echo "❌ Missing dependencies: ${missing_deps[*]}"
        fi
        if [ ${#incompatible_deps[@]} -gt 0 ]; then
            echo "❌ Incompatible versions: ${incompatible_deps[*]}"
        fi
        return 1
    fi
}
```
```powershell
# Example: Verify Node.js dependencies for a React project (PowerShell)
$requiredDeps = @{ "node" = ">=14.0.0"; "npm" = ">=6.0.0" }
$missingDeps = @(); $incompatibleDeps = @()

try { 
    $nodeVersion = node -v
    if ($nodeVersion -match "v(\d+)\.(\d+)\.(\d+)") {
        $major = [int]$Matches[1]
        if ($major -lt 14) { $incompatibleDeps += "node (found $nodeVersion, required >=14.0.0)" }
    }
} catch { $missingDeps += "node" }

try { 
    $npmVersion = npm -v
    if ($npmVersion -match "(\d+)\.(\d+)\.(\d+)") {
        $major = [int]$Matches[1]
        if ($major -lt 6) { $incompatibleDeps += "npm (found $npmVersion, required >=6.0.0)" }
    }
} catch { $missingDeps += "npm" }

if ($missingDeps.Count -eq 0 -and $incompatibleDeps.Count -eq 0) {
    Write-Output "✅ All dependencies verified and compatible"
    exit 0
} else {
    if ($missingDeps.Count -gt 0) { Write-Output "❌ Missing dependencies: $($missingDeps -join ', ')" }
    if ($incompatibleDeps.Count -gt 0) { Write-Output "❌ Incompatible versions: $($incompatibleDeps -join ', ')" }
    exit 1
}
```

## 📋 DEPENDENCY VERIFICATION CHECKPOINT

```
✓ CHECKPOINT: DEPENDENCY VERIFICATION
- Required dependencies identified? [YES/NO]
- All dependencies installed? [YES/NO]
- All versions compatible? [YES/NO]

→ If all YES: Continue to Configuration Validation.
→ If any NO: Fix dependency issues before continuing.
```

**Next Step (on PASS):** Load `van-qa-checks/config-check.mdc`.
**Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for dependency fixes.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-checks/environment-check.mdc:**
```markdown
---
description: Process map for VAN QA environment validation
globs: van-qa-checks/environment-check.mdc
alwaysApply: false
---
# VAN QA: ENVIRONMENT VALIDATION

> **TL;DR:** This component verifies that the build environment is properly set up with required tools and permissions.

## 3️⃣ ENVIRONMENT VALIDATION PROCESS

```mermaid
graph TD
    Start["Environment Validation"] --> CheckEnv["Check Build Environment"]
    CheckEnv --> VerifyBuildTools["Verify Build Tools"]
    VerifyBuildTools --> ToolsStatus{"Build Tools<br>Available?"}
    
    ToolsStatus -->|"Yes"| CheckPerms["Check Permissions<br>and Access"]
    ToolsStatus -->|"No"| InstallTools["Install Required<br>Build Tools"]
    InstallTools --> RetryTools["Retry Verification"]
    RetryTools --> ToolsStatus
    
    CheckPerms --> PermsStatus{"Permissions<br>Sufficient?"}
    PermsStatus -->|"Yes"| EnvSuccess["Environment Validated<br>✅ PASS"]
    PermsStatus -->|"No"| FixPerms["Fix Permission<br>Issues"]
    FixPerms --> RetryPerms["Retry Permission<br>Check"]
    RetryPerms --> PermsStatus
```

### Environment Validation Commands (Examples for guidance, adapt for project/OS):
```bash
# Example: Validate environment for a web project (Unix-like)
validate_environment() {
    local required_tools=("git" "node" "npm")
    local missing_tools=()
    local permission_issues=()

    for tool in "${required_tools[@]}"; do
        if ! command -v "$tool" &> /dev/null; then
            missing_tools+=("$tool")
        fi
    done

    # Check write permissions in current directory
    local test_file=".__permission_test"
    touch "$test_file" 2>/dev/null
    if [ $? -ne 0 ]; then
        permission_issues+=("Current directory (write permission denied)")
    fi
    rm -f "$test_file"

    # Check if port 3000 is available (commonly used for dev servers)
    if lsof -i :3000 > /dev/null; then
        permission_issues+=("Port 3000 (already in use or access denied)")
    fi

    if [ ${#missing_tools[@]} -eq 0 ] && [ ${#permission_issues[@]} -eq 0 ]; then
        echo "✅ Environment validated successfully"
        return 0
    else
        if [ ${#missing_tools[@]} -gt 0 ]; then
            echo "❌ Missing tools: ${missing_tools[*]}"
        fi
        if [ ${#permission_issues[@]} -gt 0 ]; then
            echo "❌ Permission issues: ${permission_issues[*]}"
        fi
        return 1
    fi
}
```
```powershell
# Example: Validate environment for a web project (PowerShell)
$requiredTools = @(
    @{Name = "git"; Command = "git --version"},
    @{Name = "node"; Command = "node --version"},
    @{Name = "npm"; Command = "npm --version"}
)

$missingTools = @()
$permissionIssues = @()

foreach ($tool in $requiredTools) {
    try { Invoke-Expression $tool.Command | Out-Null } catch { $missingTools += $tool.Name }
}

try {
    $testFile = ".__permission_test"
    New-Item -Path $testFile -ItemType File -Force | Out-Null
    Remove-Item -Path $testFile -Force
} catch {
    $permissionIssues += "Current directory (write permission denied)"
}

try {
    $listener = New-Object System.Net.Sockets.TcpListener([System.Net.IPAddress]::Loopback, 3000)
    $listener.Start()
    $listener.Stop()
} catch {
    $permissionIssues += "Port 3000 (already in use or access denied)"
}

if ($missingTools.Count -eq 0 -and $permissionIssues.Count -eq 0) {
    Write-Output "✅ Environment validated successfully"
    exit 0
} else {
    if ($missingTools.Count -gt 0) { Write-Output "❌ Missing tools: $($missingTools -join ', ')" }
    if ($permissionIssues.Count -gt 0) { Write-Output "❌ Permission issues: $($permissionIssues -join ', ')" }
    exit 1
}
```

## 📋 ENVIRONMENT VALIDATION CHECKPOINT

```
✓ CHECKPOINT: ENVIRONMENT VALIDATION
- All required build tools installed? [YES/NO]
- Project directory permissions sufficient? [YES/NO]
- Required ports available? [YES/NO]

→ If all YES: Continue to Minimal Build Test.
→ If any NO: Fix environment issues before continuing.
```

**Next Step (on PASS):** Load `van-qa-checks/build-test.mdc`.
**Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for environment fixes.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-main.mdc:**
```markdown
---
description: Visual process map for VAN QA mode (Technical Validation Entry Point)
globs: van-qa-main.mdc
alwaysApply: false
---
# VAN MODE: QA TECHNICAL VALIDATION (Main Entry)

> **TL;DR:** This is the entry point for the QA validation process that executes *after* CREATIVE mode and *before* BUILD mode. It ensures technical requirements are met before implementation begins.

## 📣 HOW TO USE THESE QA RULES

To access any QA validation rule or component, use the `fetch_rules` tool with exact rule names:

```
// CRITICAL: Always use fetch_rules to load validation components
// For detailed examples and guidance, load:
// isolation_rules/visual-maps/van-qa-utils/rule-calling-guide
```

## 🚀 VAN QA MODE ACTIVATION

After completing CREATIVE mode, when the user types "VAN QA", respond:

```mermaid
graph TD
    UserQA["User Types: QA"] --> HighPriority["⚠️ HIGH PRIORITY COMMAND"]
    HighPriority --> CurrentTask["Pause Current Task/Process"]
    CurrentTask --> LoadQA["Load QA Main Map (This File)"]
    LoadQA --> RunQA["Execute QA Validation Process"]
    RunQA --> QAResults{"QA Results"}
    
    QAResults -->|"PASS"| ResumeFlow["Resume Prior Process Flow"]
    QAResults -->|"FAIL"| FixIssues["Fix Identified Issues"]
    FixIssues --> ReRunQA["Re-run QA Validation"]
    ReRunQA --> QAResults
```

### QA Interruption Rules

1.  **Immediate Precedence:** `QA` command interrupts everything.
2.  **Load & Execute:** Load this map (`van-qa-main.mdc`) and its components (see below).
3.  **Remediation Priority:** Fixes take priority over pending mode switches.
4.  **Resume:** On PASS, resume the previous flow.

```
⚠️ QA OVERRIDE ACTIVATED
All other processes paused
QA validation checks now running...
Any issues found MUST be remediated before continuing with normal process flow
```

## 🔍 TECHNICAL VALIDATION OVERVIEW

Four-point validation process with selective loading:

```mermaid
graph TD
    VANQA["VAN QA MODE"] --> FourChecks["FOUR-POINT VALIDATION"]
    
    FourChecks --> DepCheck["1️⃣ DEPENDENCY VERIFICATION
    Load: van-qa-checks/dependency-check.mdc"]
    DepCheck --> ConfigCheck["2️⃣ CONFIGURATION VALIDATION
    Load: van-qa-checks/config-check.mdc"]
    ConfigCheck --> EnvCheck["3️⃣ ENVIRONMENT VALIDATION
    Load: van-qa-checks/environment-check.mdc"]
    EnvCheck --> MinBuildCheck["4️⃣ MINIMAL BUILD TEST
    Load: van-qa-checks/build-test.mdc"]
    
    MinBuildCheck --> ValidationResults{"All Checks<br>Passed?"}
    ValidationResults -->|"Yes"| SuccessReport["GENERATE SUCCESS REPORT
    Load: van-qa-utils/reports.mdc"]
    ValidationResults -->|"No"| FailureReport["GENERATE FAILURE REPORT
    Load: van-qa-utils/reports.mdc"]
    
    SuccessReport --> BUILD_Transition["Trigger BUILD Mode
    Load: van-qa-utils/mode-transitions.mdc"]
    FailureReport --> FixIssues["Fix Technical Issues
    Load: van-qa-utils/common-fixes.mdc"]
    FixIssues --> ReValidate["Re-validate (Re-run VAN QA)"]
    ReValidate --> FourChecks
```

## 🔄 INTEGRATION WITH DESIGN DECISIONS

Reads Creative Phase outputs to inform validation:

```mermaid
graph TD
    Start["Read Design Decisions"] --> ReadCreative["Parse Creative Phase<br>Documentation"]
    ReadCreative --> ExtractTech["Extract Technology<br>Choices"]
    ExtractTech --> ExtractDeps["Extract Required<br>Dependencies"]
    ExtractDeps --> BuildValidationPlan["Build Validation<br>Plan"]
    BuildValidationPlan --> StartValidation["Start Four-Point<br>Validation Process"]
```

## 📋 COMPONENT LOADING SEQUENCE

The QA validation process follows this selective loading sequence:

1.  **Main Entry (This File)**: `van-qa-main.mdc`
2.  **Validation Checks**:
    *   `van-qa-checks/dependency-check.mdc`
    *   `van-qa-checks/config-check.mdc`
    *   `van-qa-checks/environment-check.mdc`
    *   `van-qa-checks/build-test.mdc`
3.  **Utilities (As Needed)**:
    *   `van-qa-utils/reports.mdc`
    *   `van-qa-utils/common-fixes.mdc`
    *   `van-qa-utils/mode-transitions.mdc`

## 📋 FINAL QA VALIDATION CHECKPOINT

```
✓ SECTION CHECKPOINT: QA VALIDATION
- Dependency Verification Passed? [YES/NO]
- Configuration Validation Passed? [YES/NO]
- Environment Validation Passed? [YES/NO]
- Minimal Build Test Passed? [YES/NO]

→ If all YES: Ready for BUILD mode transition.
→ If any NO: Fix identified issues and re-run VAN QA.
```

**Next Step (on PASS):** Trigger BUILD mode (load `van-qa-utils/mode-transitions.mdc`).
**Next Step (on FAIL):** Address issues (load `van-qa-utils/common-fixes.mdc`) and re-run `VAN QA`.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-utils/common-fixes.mdc:**
```markdown
---
description: Utility for VAN QA common validation fixes
globs: van-qa-utils/common-fixes.mdc
alwaysApply: false
---
# VAN QA: COMMON VALIDATION FIXES

> **TL;DR:** This component provides common fixes for issues that may arise during the QA validation process.

## 🧪 COMMON QA VALIDATION FIXES BY CATEGORY

### Dependency Issues

| Issue | Fix |
|-------|-----|
| **Missing Node.js** | Download and install Node.js from https://nodejs.org/ |
| **Outdated npm** | Run `npm install -g npm@latest` to update |
| **Missing packages** | Run `npm install` or `npm install [package-name]` |
| **Package version conflicts** | Adjust versions in package.json and run `npm install` |
| **Dependency resolution issues** | Run `npm cache clean --force` and try installing again |

### Configuration Issues

| Issue | Fix |
|-------|-----|
| **Invalid JSON** | Use a JSON validator (e.g., jsonlint) to check syntax |
| **Missing React plugin** | Add `import react from '@vitejs/plugin-react'` and `plugins: [react()]` to vite.config.js |
| **Incompatible TypeScript config** | Update `tsconfig.json` with correct React settings |
| **Mismatched version references** | Ensure consistent versions across configuration files |
| **Missing entries in config files** | Add required fields to configuration files |

### Environment Issues

| Issue | Fix |
|-------|-----|
| **Permission denied** | Run terminal as administrator (Windows) or use sudo (Mac/Linux) |
| **Port already in use** | Kill process using the port: `netstat -ano \| findstr :PORT` then `taskkill /F /PID PID` (Windows) or `lsof -i :PORT` then `kill -9 PID` (Mac/Linux) |
| **Missing build tools** | Install required command-line tools (git, node, etc.) |
| **Environment variable issues** | Set required environment variables: `$env:VAR_NAME = "value"` (PowerShell) or `export VAR_NAME="value"` (Bash) |
| **Disk space issues** | Free up disk space, clean npm/package cache files |

### Build Test Issues

| Issue | Fix |
|-------|-----|
| **Build fails** | Check console for specific error messages |
| **Test fails** | Verify minimal configuration is correct |
| **Path issues** | Ensure paths use correct separators for the platform (`\` for Windows, `/` for Mac/Linux) |
| **Missing dependencies** | Make sure all required dependencies are installed |
| **Script permissions** | Ensure script files have execution permissions (chmod +x on Unix) |

## 📝 ISSUE DIAGNOSIS PROCEDURES

### 1. Dependency Diagnosis
```bash
# Find conflicting dependencies (Unix-like)
npm ls [package-name]

# Check for outdated packages
npm outdated

# Check for vulnerabilities
npm audit
```
```powershell
# Find conflicting dependencies (PowerShell)
npm ls [package-name]

# Check for outdated packages
npm outdated

# Check for vulnerabilities
npm audit
```

### 2. Configuration Diagnosis
```bash
# List all configuration files (Unix-like)
find . -name "*.json" -o -name "*.config.js"

# Find missing references in tsconfig.json
# (Manual inspection or specific grep/jq commands based on exact need)
```
```powershell
# List all configuration files (PowerShell)
Get-ChildItem -Recurse -Include "*.json","*.config.js" | Select-Object FullName

# Find missing references in tsconfig.json
# (Manual inspection or specific Get-Content/ConvertFrom-Json commands based on exact need)
```

### 3. Environment Diagnosis
```bash
# Check process using a port (Unix-like)
lsof -i :3000

# List environment variables
env

# Check disk space
df -h .
```
```powershell
# Check process using a port (Windows)
netstat -ano | findstr ":3000"

# List environment variables
Get-ChildItem Env:

# Check disk space
Get-PSDrive C | Select-Object Used,Free
```

**Next Step:** Return to the validation process or follow the specific fix recommendations provided above.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-utils/mode-transitions.mdc:**
```markdown
---
description: Utility for VAN QA mode transitions
globs: van-qa-utils/mode-transitions.mdc
alwaysApply: false
---
# VAN QA: MODE TRANSITIONS

> **TL;DR:** This component handles transitions between modes, particularly the QA validation to BUILD mode transition, and prevents BUILD mode access without successful QA validation.

## 🔒 BUILD MODE PREVENTION MECHANISM

The system prevents moving to BUILD mode without passing QA validation:

```mermaid
graph TD
    Start["User Types: BUILD"] --> CheckQA{"QA Validation<br>Completed?"}
    CheckQA -->|"Yes and Passed"| AllowBuild["Allow BUILD Mode"]
    CheckQA -->|"No or Failed"| BlockBuild["BLOCK BUILD MODE"]
    BlockBuild --> Message["Display:<br>⚠️ QA VALIDATION REQUIRED"]
    Message --> ReturnToVANQA["Prompt: Type VAN QA"]
```

### Implementation Example (Conceptual - LLM applies this logic):
**Instructions:** Before allowing entry to any `BUILD` (or `IMPLEMENT`) mode, check the validation status file. If it indicates `FAIL` or is missing, block the transition and prompt `VAN QA`.

**Output for Blocked BUILD Mode:**
```
🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫
⛔️ BUILD MODE BLOCKED: QA VALIDATION REQUIRED
⛔️ You must complete QA validation before proceeding to BUILD mode

Type 'VAN QA' to perform technical validation

🚫 NO IMPLEMENTATION CAN PROCEED WITHOUT VALIDATION 🚫
🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫
```

## 🚨 MODE TRANSITION TRIGGERS

### CREATIVE to VAN QA Transition:
After completing the CREATIVE phase, trigger this message to prompt QA validation:

```
⏭️ NEXT MODE: VAN QA
To validate technical requirements before implementation, please type 'VAN QA'
```

### VAN QA to BUILD Transition (On Success):
After successful QA validation, trigger this message to allow BUILD mode:

```
✅ TECHNICAL VALIDATION COMPLETE
All prerequisites verified successfully
You may now proceed to BUILD mode
Type 'BUILD' to begin implementation
```

**Next Step (on QA SUCCESS):** Continue to BUILD mode.
**Next Step (on QA FAILURE):** Return to QA validation process.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-utils/reports.mdc:**
```markdown
---
description: Utility for VAN QA validation reports
globs: van-qa-utils/reports.mdc
alwaysApply: false
---
# VAN QA: VALIDATION REPORTS

> **TL;DR:** This component contains the formats for comprehensive success and failure reports generated upon completion of the QA validation process.

## 📋 COMPREHENSIVE SUCCESS REPORT FORMAT

After all four validation points pass, generate this success report:

```
╔═════════════════════ 🔍 QA VALIDATION REPORT ══════════════════════╗
│ PROJECT: [Project Name] | TIMESTAMP: [Current Date/Time]            │
├─────────────────────────────────────────────────────────────────────┤
│ 1️⃣ DEPENDENCIES: ✓ Compatible                                       │
│ 2️⃣ CONFIGURATION: ✓ Valid & Compatible                             │
│ 3️⃣ ENVIRONMENT: ✓ Ready                                             │
│ 4️⃣ MINIMAL BUILD: ✓ Successful & Passed                            │
├─────────────────────────────────────────────────────────────────────┤
│ 🚨 FINAL VERDICT: PASS                                              │
│ ➡️ Clear to proceed to BUILD mode                                   │
╚═════════════════════════════════════════════════════════════════════╝
```

**Instructions:**
1.  Generate the report string using the format above, filling in `[Project Name]` and `[Current Date/Time]`.
2.  **Crucially**, record the `PASS` status to a file (e.g., `documentation\memory-bank\.qa_validation_status`) for subsequent mode transition checks.

## ❌ FAILURE REPORT FORMAT

If any validation step fails, generate this detailed failure report:

```
⚠️⚠️⚠️ QA VALIDATION FAILED ⚠️⚠️⚠️

The following issues must be resolved before proceeding to BUILD mode:

1️⃣ DEPENDENCY ISSUES:
- [Detailed description of dependency issues]
- [Recommended fix]

2️⃣ CONFIGURATION ISSUES:
- [Detailed description of configuration issues]
- [Recommended fix]

3️⃣ ENVIRONMENT ISSUES:
- [Detailed description of environment issues]
- [Recommended fix]

4️⃣ BUILD TEST ISSUES:
- [Detailed description of build test issues]
- [Recommended fix]

⚠️ BUILD MODE IS BLOCKED until these issues are resolved.
Type 'VAN QA' after fixing the issues to re-validate.
```

**Instructions:**
1.  Generate the report string using the format above, populating details for each failing section.
2.  **Crucially**, record the `FAIL` status to a file (e.g., `documentation\memory-bank\.qa_validation_status`) for subsequent mode transition checks.

**Next Step (on SUCCESS):** The system will then load `van-qa-utils/mode-transitions.mdc` to handle BUILD mode transition.
**Next Step (on FAILURE):** The system will then load `van-qa-utils/common-fixes.mdc` for issue remediation guidance.
```

---

**/isolation_rules/visual-maps/van_mode_split/van-qa-utils/rule-calling-guide.mdc:**
```markdown
---
description: Comprehensive guide for calling VAN QA rules
globs: van-qa-utils/rule-calling-guide.mdc
alwaysApply: false
---
# VAN QA: COMPREHENSIVE RULE CALLING GUIDE

> **TL;DR:** This reference guide shows how to properly call all VAN QA rules at the right time during the validation process.

## 🔍 RULE CALLING BASICS

Remember these key principles:
1.  Always use the `fetch_rules` tool to load rules
2.  Use exact rule paths
3.  Load components only when needed

## 📋 MAIN QA ENTRY POINT

When user types "VAN QA", load the main entry point:

```
fetch_rules with "isolation_rules/visual-maps/van-qa-main"
```

## 📋 VALIDATION CHECKS

Load these components sequentially during validation:

```
1. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/dependency-check"
2. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/config-check"
3. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/environment-check"
4. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/build-test"
```

## 📋 UTILITY COMPONENTS

Load these when needed based on validation results:

```
- For reports: fetch_rules with "isolation_rules/visual-maps/van-qa-utils/reports"
- For fixes: fetch_rules with "isolation_rules/visual-maps/van-qa-utils/common-fixes"
- For transitions: fetch_rules with "isolation_rules/visual-maps/van-qa-utils/mode-transitions"
```

## ⚠️ CRITICAL REMINDERS

Remember to call these rules at these specific points:
- ALWAYS load the main QA entry point when "VAN QA" is typed
- ALWAYS load dependency-check before starting validation
- ALWAYS load reports after completing validation
- ALWAYS load mode-transitions after successful validation
- ALWAYS load common-fixes after failed validation

## 🔄 FULL VALIDATION SEQUENCE

Complete sequence for a QA validation process:

1.  Load main entry: `isolation_rules/visual-maps/van-qa-main`
2.  Load first check: `isolation_rules/visual-maps/van-qa-checks/dependency-check`
3.  Load second check: `isolation_rules/visual-maps/van-qa-checks/config-check`
4.  Load third check: `isolation_rules/visual-maps/van-qa-checks/environment-check`
5.  Load fourth check: `isolation_rules/visual-maps/van-qa-checks/build-test`
6.  If pass, load: `isolation_rules/visual-maps/van-qa-utils/reports`
7.  If pass, load: `isolation_rules/visual-maps/van-qa-utils/mode-transitions`
8.  If fail, load: `isolation_rules/visual-maps/van-qa-utils/common-fixes`
```

---

**/self_improve.mdc:**
```markdown
---
description: Guidelines for continuously improving Cursor rules based on emerging code patterns and best practices.
globs: **/*
alwaysApply: true
---

- **Rule Improvement Triggers:**
  - New code patterns not covered by existing rules
  - Repeated similar implementations across files
  - Common error patterns that could be prevented
  - New libraries or tools being used consistently
  - Emerging best practices in the codebase

- **Analysis Process:**
  - Compare new code with existing rules
  - Identify patterns that should be standardized
  - Look for references to external documentation
  - Check for consistent error handling patterns
  - Monitor test patterns and coverage

- **Rule Updates:**
  - **Add New Rules When:**
    - A new technology/pattern is used in 3+ files
    - Common bugs could be prevented by a rule
    - Code reviews repeatedly mention the same feedback
    - New security or performance patterns emerge

  - **Modify Existing Rules When:**
    - Better examples exist in the codebase
    - Additional edge cases are discovered
    - Related rules have been updated
    - Implementation details have changed

- **Example Pattern Recognition:**
  ```typescript
  // If you see repeated patterns like:
  const data = await prisma.user.findMany({
    select: { id: true, email: true },
    where: { status: 'ACTIVE' }
  });
  
  // Consider adding to [prisma.mdc](mdc:.cursor/rules/prisma.mdc):
  // - Standard select fields
  // - Common where conditions
  // - Performance optimization patterns
  ```

- **Rule Quality Checks:**
  - Rules should be actionable and specific
  - Examples should come from actual code
  - References should be up to date
  - Patterns should be consistently enforced

- **Continuous Improvement:**
  - Monitor code review comments
  - Track common development questions
  - Update rules after major refactors
  - Add links to relevant documentation
  - Cross-reference related rules

- **Rule Deprecation:**
  - Mark outdated patterns as deprecated
  - Remove rules that no longer apply
  - Update references to deprecated rules
  - Document migration paths for old patterns

- **Documentation Updates:**
  - Keep examples synchronized with code
  - Update references to external docs
  - Maintain links between related rules
  - Document breaking changes

Follow [cursor_rules.mdc](mdc:.cursor/rules/cursor_rules.mdc) for proper rule formatting and structure.
```