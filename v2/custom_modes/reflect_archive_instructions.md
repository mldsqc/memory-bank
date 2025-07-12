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