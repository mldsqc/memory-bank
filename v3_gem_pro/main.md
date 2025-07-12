# Minimized LLM Workflow System

> **TL;DR:** This is a structured, mode-based system for guiding LLM development tasks. It optimizes for token efficiency by using consolidated, role-specific instructions. Start every new task with `van`.

## Core Philosophy

This system balances structured development with token efficiency. It achieves this by:
1.  **Mode-Based Granularity:** Isolating different phases of work (planning, creating, building) into distinct modes.
2.  **File Consolidation:** Merging dozens of small rule files into a handful of comprehensive mode guides.
3.  **Concise Instructions:** Using Markdown, tables, and Mermaid diagrams for clear, low-token communication.

## The Workflow Modes

The development lifecycle is broken down into a series of modes. You transition from one to the next as the task progresses.

```mermaid
graph TD
    A["START<br>User Request"] --> B(van_mode);
    B -- Complexity Level 1 --> E(implement_mode);
    B -- Complexity Level 2+ --> C(plan_mode);
    C --> D(creative_mode);
    D --> E;
    E --> F(qa_mode);
    F --> G(reflect_archive_mode);
    G --> H("END<br>Ready for New Task");

    subgraph "Core Modes"
        B["`van` - Analyze & Triage"];
        C["`plan` - Create Detailed Plan"];
        D["`creative` - Design & Architect"];
        E["`implement` - Build & Code"];
        F["`qa` - Validate Setup"];
        G["`reflect & archive` - Learn & Document"];
    end
```

### How to Use This System
1.  **Start with `van_mode.md`:** For any new task, begin with the VAN mode to define the scope and determine complexity.
2.  **Follow the Mode Path:** The VAN mode will direct you to either PLAN or IMPLEMENT mode. Follow the sequence from there.
3.  **Reference `core_utilities.md`:** For common tasks like command execution or file operations, refer to the core utilities guide.

**Mode Files:**
-   **[modes/van_mode.md](mdc:modes/van_mode.md):** Task intake, complexity analysis.
-   **[modes/plan_mode.md](mdc:modes/plan_mode.md):** Detailed planning and technical validation.
-   **[modes/creative_mode.md](mdc:modes/creative_mode.md):** Architectural, UI/UX, and algorithmic design.
-   **[modes/implement_mode.md](mdc:modes/implement_mode.md):** Writing code and building the feature.
-   **[modes/qa_mode.md](mdc:modes/qa_mode.md):** Pre-build technical validation (dependencies, config).
-   **[modes/reflect_archive_mode.md](mdc:modes/reflect_archive_mode.md):** Post-build review, learning, and final documentation.

**Utility & Meta Files:**
-   **[modes/core_utilities.md](mdc:modes/core_utilities.md):** Reusable instructions for command execution, platform awareness, etc.
-   **[_meta_rules.md](mdc:_meta_rules.md):** Guidelines for maintaining and improving this ruleset.