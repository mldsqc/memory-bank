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