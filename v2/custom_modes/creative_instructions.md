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