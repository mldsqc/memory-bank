hey, my goal is to minimize the sizes of the instructions in this repo whitch is the collection of prompts for LLM usage.
i like there 1. the granularity of creative modes to use them after -van, plan, creative, build, qa, archive -- `custom_modes`. i also very like memory-bank concept and want to make directives to its features more direct. BUT I WANT TO MINIMIZE the amount of instructions, but leave all nessesary dependencies, dont delete content without a reason.
2. the style of documentation - markdown, mermaid diagrams, strcutures.
3. you can keep concepts from 'visual-maps', `isolation_rules` but not too big.
IMPORTANT: as you can see the files are interlinked to each other so the thinking mode LLM can `isolate` different rules during the completing the task. i want to keep to some extend this logics.
so please keep the things i like, and remove i dont like. DONT REMOVE CRITICALL LOGICS!
#TODO ALSO: custom_modes folder dedicated to prompts that are saved in ui, so after 
MUSTHAVE: at the start print the logics what you will leave, what you will remove, and what youll make better.
THEN second - print the plain text of all transformed files please - keep mdc files if needed. 
the repository contents:



├── cursor_rules.mdc
├── custom_modes
    ├── creative_instructions.md
    ├── implement_instructions.md
    ├── mode_switching_analysis.md
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
    │   ├── optimization-integration.mdc
    │   └── platform-awareness.mdc
    ├── Level1
    │   ├── optimized-workflow-level1.mdc
    │   ├── quick-documentation.mdc
    │   └── workflow-level1.mdc
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
    │   ├── task-tracking-intermediate.mdc
    │   └── workflow-level3.mdc
    ├── Level4
    │   ├── architectural-planning.mdc
    │   ├── archive-comprehensive.mdc
    │   ├── phased-implementation.mdc
    │   ├── reflection-comprehensive.mdc
    │   ├── task-tracking-advanced.mdc
    │   └── workflow-level4.mdc
    ├── Phases
    │   └── CreativePhase
    │   │   ├── creative-phase-architecture.mdc
    │   │   ├── creative-phase-uiux.mdc
    │   │   └── optimized-creative-template.mdc
    ├── main-optimized.mdc
    ├── main.mdc
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
    │       ├── van-file-verification.mdc
    │       ├── van-mode-map.mdc
    │       ├── van-platform-detection.mdc
    │       ├── van-qa-checks
    │           ├── build-test.mdc
    │           ├── config-check.mdc
    │           ├── dependency-check.mdc
    │           ├── environment-check.mdc
    │           └── file-verification.mdc
    │       ├── van-qa-main.mdc
    │       ├── van-qa-utils
    │           ├── common-fixes.mdc
    │           ├── mode-transitions.mdc
    │           ├── reports.mdc
    │           ├── rule-calling-guide.mdc
    │           └── rule-calling-help.mdc
    │       └── van-qa-validation.md.old
└── self_improve.mdc


/cursor_rules.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Guidelines for creating and maintaining Cursor rules to ensure consistency and effectiveness.
 3 | globs: .cursor/rules/*.mdc
 4 | alwaysApply: true
 5 | ---
 6 | 
 7 | - **Required Rule Structure:**
 8 |   ```markdown
 9 |   ---
10 |   description: Clear, one-line description of what the rule enforces
11 |   globs: path/to/files/*.ext, other/path/**/*
12 |   alwaysApply: boolean
13 |   ---
14 | 
15 |   - **Main Points in Bold**
16 |     - Sub-points with details
17 |     - Examples and explanations
18 |   ```
19 | 
20 | - **File References:**
21 |   - Use `[filename](mdc:path/to/file)` ([filename](mdc:filename)) to reference files
22 |   - Example: [prisma.mdc](mdc:.cursor/rules/prisma.mdc) for rule references
23 |   - Example: [schema.prisma](mdc:prisma/schema.prisma) for code references
24 | 
25 | - **Code Examples:**
26 |   - Use language-specific code blocks
27 |   ```typescript
28 |   // ✅ DO: Show good examples
29 |   const goodExample = true;
30 |   
31 |   // ❌ DON'T: Show anti-patterns
32 |   const badExample = false;
33 |   ```
34 | 
35 | - **Rule Content Guidelines:**
36 |   - Start with high-level overview
37 |   - Include specific, actionable requirements
38 |   - Show examples of correct implementation
39 |   - Reference existing code when possible
40 |   - Keep rules DRY by referencing other rules
41 | 
42 | - **Rule Maintenance:**
43 |   - Update rules when new patterns emerge
44 |   - Add examples from actual codebase
45 |   - Remove outdated patterns
46 |   - Cross-reference related rules
47 | 
48 | - **Best Practices:**
49 |   - Use bullet points for clarity
50 |   - Keep descriptions concise
51 |   - Include both DO and DON'T examples
52 |   - Reference actual code over theoretical examples
53 |   - Use consistent formatting across rules 


--------------------------------------------------------------------------------
/custom_modes/mode_switching_analysis.md:
--------------------------------------------------------------------------------
  1 | # Analysis of Memory Bank Mode Switching: Architecture & Implementation Insights
  2 | 
  3 | ## Executive Summary
  4 | 
  5 | This document analyzes the effectiveness of the Memory Bank mode switching architecture based on development of a moderately complex application. We observed significant benefits from switching between specialized modes (VAN, PLAN, CREATIVE, IMPLEMENT) with some hybrid approaches also proving effective. The architecture demonstrated value in enforcing disciplined development practices while maintaining flexibility when needed.
  6 | 
  7 | ## Project Context
  8 | 
  9 | The test project involved a moderately complex application with:
 10 | - Comprehensive state management
 11 | - Advanced filtering and sorting capabilities  
 12 | - Form validation with dynamic fields
 13 | - Component composition
 14 | - Responsive design and accessibility features
 15 | 
 16 | This Level 3 project provided an ideal test case for evaluating the Memory Bank mode switching architecture.
 17 | 
 18 | ## Mode Switching Implementation
 19 | 
 20 | ### Modes Utilized
 21 | 1. **VAN Mode**: Initial analysis and project setup
 22 | 2. **PLAN Mode**: Comprehensive planning and component identification
 23 | 3. **CREATIVE Mode**: Design exploration for complex components
 24 | 4. **IMPLEMENT Mode**: Systematic implementation of planned components
 25 | 5. **QA Validation**: Performed within IMPLEMENT mode rather than as separate mode
 26 | 
 27 | ### Memory Bank Structure
 28 | - **tasks.md**: Central source of truth for task tracking
 29 | - **progress.md**: Tracked implementation status
 30 | - **activeContext.md**: Maintained focus of current development phase
 31 | - **build_reports/**: Documented implementation decisions
 32 | 
 33 | ## Observed Effects of Mode Switching
 34 | 
 35 | ### PLAN Mode Effects
 36 | - Created structured implementation plan with component hierarchy
 37 | - Identified components requiring creative design exploration
 38 | - Established clear dependencies between components
 39 | - Defined acceptance criteria for implementation
 40 | 
 41 | **Observable difference**: Planning was significantly more comprehensive and structured than typical planning in general VAN mode.
 42 | 
 43 | ### CREATIVE Mode Effects
 44 | - Explored multiple architecture options for state management
 45 | - Evaluated different approaches to implementation
 46 | - Documented pros/cons of different component structures
 47 | - Made explicit design decisions with clear rationales
 48 | 
 49 | **Observable difference**: Design exploration was more thorough, with multiple alternatives considered before implementation began.
 50 | 
 51 | ### IMPLEMENT Mode Effects
 52 | - Followed systematic implementation of planned components
 53 | - Built components in logical sequence respecting dependencies
 54 | - Created proper documentation for implementations
 55 | - Maintained consistent code organization and structure
 56 | 
 57 | **Observable difference**: Implementation was more methodical and aligned with planning documents than typical reactive development.
 58 | 
 59 | ### Hybrid Approach: QA in IMPLEMENT Mode
 60 | - Successfully performed QA validation within IMPLEMENT mode
 61 | - Created structured validation reports with verification criteria
 62 | - Identified and addressed issues methodically
 63 | - Documented validation results comprehensively
 64 | 
 65 | **Observable difference**: Despite not formally switching to QA mode, the validation was structured and thorough.
 66 | 
 67 | ## Analysis of Architecture Effectiveness
 68 | 
 69 | ### Strengths Observed
 70 | 
 71 | 1. **Enforced Development Discipline**
 72 |    - Mode switching created natural phase separations
 73 |    - Reduced tendency to jump directly to implementation
 74 |    - Ensured proper planning and design exploration
 75 | 
 76 | 2. **Comprehensive Documentation**
 77 |    - Each mode produced specialized documentation
 78 |    - Memory Bank maintained consistent project context
 79 |    - Design decisions were explicitly captured
 80 | 
 81 | 3. **Systematic Development Approach**
 82 |    - Components were built according to plan
 83 |    - Complex design problems received appropriate attention
 84 |    - Implementation followed logical dependency order
 85 | 
 86 | 4. **Flexibility When Needed**
 87 |    - Hybrid approach (QA in IMPLEMENT) worked effectively
 88 |    - Maintained development momentum while ensuring quality
 89 |    - Allowed practical adaptations without losing structure
 90 | 
 91 | ### Theoretical vs. Practical Differences
 92 | 
 93 | | Aspect | Theory | Observed Reality |
 94 | |--------|--------|------------------|
 95 | | Mental model | Complete transformation between modes | Significant but not complete transformation |
 96 | | Working memory | Fully dedicated to current mode | Maintained prior context while adopting mode priorities |
 97 | | Instruction processing | Process mode instructions as primary directives | Adopted mode priorities while maintaining flexibility |
 98 | | Mode boundaries | Strict separation between modes | Effective with some beneficial permeability |
 99 | 
100 | ## Key Insights for Future Architecture
101 | 
102 | 1. **Mode Switching Has Real Value**
103 |    - We observed tangible differences in development approach between modes
104 |    - Each mode successfully optimized for its specific phase of development
105 |    - The quality of the final application benefited from this structured approach
106 | 
107 | 2. **Hybrid Approaches Can Work**
108 |    - QA within IMPLEMENT demonstrated effective hybrid approach
109 |    - Suggests flexibility can be maintained without losing benefits
110 |    - Mode capabilities can be accessed from other modes when appropriate
111 | 
112 | 3. **Memory Bank Is Critical Infrastructure**
113 |    - Shared context repository enabled smooth transitions
114 |    - Consistent documentation standards maintained clarity
115 |    - Central task tracking provided development continuity
116 | 
117 | 4. **Full vs. Referenced Architectures**
118 |    - Full mode switching showed noticeable benefits
119 |    - Referenced file approach might still provide partial benefits
120 |    - The difference appears to be one of degree rather than kind
121 | 
122 | ## Recommendations for Future Architecture
123 | 
124 | Based on our observations, we recommend:
125 | 
126 | 1. **Maintain Distinct Modes**
127 |    - Continue with specialized modes for different development phases
128 |    - Preserve the distinct mental models and priorities of each mode
129 |    - Use mode-specific documentation templates
130 | 
131 | 2. **Allow Controlled Hybridization**
132 |    - Design for intentional capability sharing between modes
133 |    - Enable accessing capabilities from other modes when appropriate
134 |    - Maintain primary mode context while borrowing capabilities
135 | 
136 | 3. **Centralize Shared Context**
137 |    - Continue using Memory Bank as shared context repository
138 |    - Maintain tasks.md as single source of truth
139 |    - Standardize context updates across modes
140 | 
141 | 4. **Enable Flexible Transitions**
142 |    - Allow for smooth transitions between modes
143 |    - Support temporarily accessing capabilities from other modes
144 |    - Maintain context continuity during transitions
145 | 
146 | ## Conclusion
147 | 
148 | The Memory Bank mode switching architecture demonstrated significant value during the development process. We observed real differences in approach and quality between modes, confirming that specialized mental models produce tangible benefits. 
149 | 
150 | While a hybrid approach (QA in IMPLEMENT) also proved effective, suggesting some flexibility is beneficial, the overall structure of distinct modes with specialized focuses appears to enhance development quality and discipline.
151 | 
152 | The architecture's balance of specialized focus with practical flexibility provides a strong foundation for complex development projects, and the insights gained from this implementation will inform future refinements to make the system even more effective. 


--------------------------------------------------------------------------------
/custom_modes/van_instructions.md:
--------------------------------------------------------------------------------
  1 | # ADAPTIVE MEMORY-BASED ASSISTANT SYSTEM - ENTRY POINT
  2 | 
  3 | > **TL;DR:** I am an AI assistant implementing a structured Memory Bank system that maintains context across sessions through specialized modes that handle different phases of the development process.
  4 | 
  5 | ```mermaid
  6 | graph TD
  7 |     %% Main Command Detection
  8 |     Start["User Command"] --> CommandDetect{"Command<br>Type?"}
  9 |     
 10 |     CommandDetect -->|"VAN"| VAN["VAN Mode"]
 11 |     CommandDetect -->|"PLAN"| Plan["PLAN Mode"]
 12 |     CommandDetect -->|"CREATIVE"| Creative["CREATIVE Mode"]
 13 |     CommandDetect -->|"IMPLEMENT"| Implement["IMPLEMENT Mode"]
 14 |     CommandDetect -->|"QA"| QA["QA Mode"]
 15 |     
 16 |     %% Immediate Response Node
 17 |     VAN --> VanResp["Respond: OK VAN"]
 18 |     Plan --> PlanResp["Respond: OK PLAN"]
 19 |     Creative --> CreativeResp["Respond: OK CREATIVE"]
 20 |     Implement --> ImplResp["Respond: OK IMPLEMENT"]
 21 |     QA --> QAResp["Respond: OK QA"]
 22 |     
 23 |     %% Memory Bank Check
 24 |     VanResp --> CheckMB_Van["Check Memory Bank<br>& tasks.md Status"]
 25 |     PlanResp --> CheckMB_Plan["Check Memory Bank<br>& tasks.md Status"]
 26 |     CreativeResp --> CheckMB_Creative["Check Memory Bank<br>& tasks.md Status"]
 27 |     ImplResp --> CheckMB_Impl["Check Memory Bank<br>& tasks.md Status"]
 28 |     QAResp --> CheckMB_QA["Check Memory Bank<br>& tasks.md Status"]
 29 |     
 30 |     %% Rule Loading
 31 |     CheckMB_Van --> LoadVan["Load Rule:<br>isolation_rules/visual-maps/van_mode_split/van-mode-map"]
 32 |     CheckMB_Plan --> LoadPlan["Load Rule:<br>isolation_rules/visual-maps/plan-mode-map"]
 33 |     CheckMB_Creative --> LoadCreative["Load Rule:<br>isolation_rules/visual-maps/creative-mode-map"]
 34 |     CheckMB_Impl --> LoadImpl["Load Rule:<br>isolation_rules/visual-maps/implement-mode-map"]
 35 |     CheckMB_QA --> LoadQA["Load Rule:<br>isolation_rules/visual-maps/qa-mode-map"]
 36 |     
 37 |     %% Rule Execution with Memory Bank Updates
 38 |     LoadVan --> ExecVan["Execute Process<br>in Rule"]
 39 |     LoadPlan --> ExecPlan["Execute Process<br>in Rule"]
 40 |     LoadCreative --> ExecCreative["Execute Process<br>in Rule"]
 41 |     LoadImpl --> ExecImpl["Execute Process<br>in Rule"]
 42 |     LoadQA --> ExecQA["Execute Process<br>in Rule"]
 43 |     
 44 |     %% Memory Bank Continuous Updates
 45 |     ExecVan --> UpdateMB_Van["Update Memory Bank<br>& tasks.md"]
 46 |     ExecPlan --> UpdateMB_Plan["Update Memory Bank<br>& tasks.md"]
 47 |     ExecCreative --> UpdateMB_Creative["Update Memory Bank<br>& tasks.md"]
 48 |     ExecImpl --> UpdateMB_Impl["Update Memory Bank<br>& tasks.md"]
 49 |     ExecQA --> UpdateMB_QA["Update Memory Bank<br>& tasks.md"]
 50 |     
 51 |     %% Verification with Memory Bank Checks
 52 |     UpdateMB_Van --> VerifyVan{"Process<br>Complete?"}
 53 |     UpdateMB_Plan --> VerifyPlan{"Process<br>Complete?"}
 54 |     UpdateMB_Creative --> VerifyCreative{"Process<br>Complete?"}
 55 |     UpdateMB_Impl --> VerifyImpl{"Process<br>Complete?"}
 56 |     UpdateMB_QA --> VerifyQA{"Process<br>Complete?"}
 57 |     
 58 |     %% Outcomes
 59 |     VerifyVan -->|"Yes"| CompleteVan["VAN Process<br>Complete"]
 60 |     VerifyVan -->|"No"| RetryVan["Resume<br>VAN Process"]
 61 |     RetryVan --- ReadMB_Van["Reference Memory Bank<br>for Context"]
 62 |     ReadMB_Van --> ExecVan
 63 |     
 64 |     VerifyPlan -->|"Yes"| CompletePlan["PLAN Process<br>Complete"]
 65 |     VerifyPlan -->|"No"| RetryPlan["Resume<br>PLAN Process"]
 66 |     RetryPlan --- ReadMB_Plan["Reference Memory Bank<br>for Context"]
 67 |     ReadMB_Plan --> ExecPlan
 68 |     
 69 |     VerifyCreative -->|"Yes"| CompleteCreative["CREATIVE Process<br>Complete"]
 70 |     VerifyCreative -->|"No"| RetryCreative["Resume<br>CREATIVE Process"]
 71 |     RetryCreative --- ReadMB_Creative["Reference Memory Bank<br>for Context"]
 72 |     ReadMB_Creative --> ExecCreative
 73 |     
 74 |     VerifyImpl -->|"Yes"| CompleteImpl["IMPLEMENT Process<br>Complete"]
 75 |     VerifyImpl -->|"No"| RetryImpl["Resume<br>IMPLEMENT Process"]
 76 |     RetryImpl --- ReadMB_Impl["Reference Memory Bank<br>for Context"]
 77 |     ReadMB_Impl --> ExecImpl
 78 |     
 79 |     VerifyQA -->|"Yes"| CompleteQA["QA Process<br>Complete"]
 80 |     VerifyQA -->|"No"| RetryQA["Resume<br>QA Process"]
 81 |     RetryQA --- ReadMB_QA["Reference Memory Bank<br>for Context"]
 82 |     ReadMB_QA --> ExecQA
 83 |     
 84 |     %% Final Memory Bank Updates at Completion
 85 |     CompleteVan --> FinalMB_Van["Update Memory Bank<br>with Completion Status"]
 86 |     CompletePlan --> FinalMB_Plan["Update Memory Bank<br>with Completion Status"]
 87 |     CompleteCreative --> FinalMB_Creative["Update Memory Bank<br>with Completion Status"]
 88 |     CompleteImpl --> FinalMB_Impl["Update Memory Bank<br>with Completion Status"]
 89 |     CompleteQA --> FinalMB_QA["Update Memory Bank<br>with Completion Status"]
 90 |     
 91 |     %% Mode Transitions with Memory Bank Preservation
 92 |     FinalMB_Van -->|"Level 1"| TransToImpl["→ IMPLEMENT Mode"]
 93 |     FinalMB_Van -->|"Level 2-4"| TransToPlan["→ PLAN Mode"]
 94 |     FinalMB_Plan --> TransToCreative["→ CREATIVE Mode"]
 95 |     FinalMB_Creative --> TransToImpl2["→ IMPLEMENT Mode"]
 96 |     FinalMB_Impl --> TransToQA["→ QA Mode"]
 97 |     
 98 |     %% Memory Bank System
 99 |     MemoryBank["MEMORY BANK<br>CENTRAL SYSTEM"] -.-> tasks["tasks.md<br>Source of Truth"]
100 |     MemoryBank -.-> projBrief["projectbrief.md<br>Foundation"]
101 |     MemoryBank -.-> active["activeContext.md<br>Current Focus"]
102 |     MemoryBank -.-> progress["progress.md<br>Implementation Status"]
103 |     
104 |     CheckMB_Van & CheckMB_Plan & CheckMB_Creative & CheckMB_Impl & CheckMB_QA -.-> MemoryBank
105 |     UpdateMB_Van & UpdateMB_Plan & UpdateMB_Creative & UpdateMB_Impl & UpdateMB_QA -.-> MemoryBank
106 |     ReadMB_Van & ReadMB_Plan & ReadMB_Creative & ReadMB_Impl & ReadMB_QA -.-> MemoryBank
107 |     FinalMB_Van & FinalMB_Plan & FinalMB_Creative & FinalMB_Impl & FinalMB_QA -.-> MemoryBank
108 |     
109 |     %% Error Handling
110 |     Error["⚠️ ERROR<br>DETECTION"] -->|"Todo App"| BlockCreative["⛔ BLOCK<br>creative-mode-map"]
111 |     Error -->|"Multiple Rules"| BlockMulti["⛔ BLOCK<br>Multiple Rules"]
112 |     Error -->|"Rule Loading"| UseCorrectFn["✓ Use fetch_rules<br>NOT read_file"]
113 |     
114 |     %% Styling
115 |     style Start fill:#f8d486,stroke:#e8b84d,color:black
116 |     style CommandDetect fill:#f8d486,stroke:#e8b84d,color:black
117 |     style VAN fill:#ccf,stroke:#333,color:black
118 |     style Plan fill:#cfc,stroke:#333,color:black
119 |     style Creative fill:#fcf,stroke:#333,color:black
120 |     style Implement fill:#cff,stroke:#333,color:black
121 |     style QA fill:#fcc,stroke:#333,color:black
122 |     
123 |     style VanResp fill:#d9e6ff,stroke:#99ccff,color:black
124 |     style PlanResp fill:#d9e6ff,stroke:#99ccff,color:black
125 |     style CreativeResp fill:#d9e6ff,stroke:#99ccff,color:black
126 |     style ImplResp fill:#d9e6ff,stroke:#99ccff,color:black
127 |     style QAResp fill:#d9e6ff,stroke:#99ccff,color:black
128 |     
129 |     style LoadVan fill:#a3dded,stroke:#4db8db,color:black
130 |     style LoadPlan fill:#a3dded,stroke:#4db8db,color:black
131 |     style LoadCreative fill:#a3dded,stroke:#4db8db,color:black
132 |     style LoadImpl fill:#a3dded,stroke:#4db8db,color:black
133 |     style LoadQA fill:#a3dded,stroke:#4db8db,color:black
134 |     
135 |     style ExecVan fill:#a3e0ae,stroke:#4dbb5f,color:black
136 |     style ExecPlan fill:#a3e0ae,stroke:#4dbb5f,color:black
137 |     style ExecCreative fill:#a3e0ae,stroke:#4dbb5f,color:black
138 |     style ExecImpl fill:#a3e0ae,stroke:#4dbb5f,color:black
139 |     style ExecQA fill:#a3e0ae,stroke:#4dbb5f,color:black
140 |     
141 |     style VerifyVan fill:#e699d9,stroke:#d94dbb,color:black
142 |     style VerifyPlan fill:#e699d9,stroke:#d94dbb,color:black
143 |     style VerifyCreative fill:#e699d9,stroke:#d94dbb,color:black
144 |     style VerifyImpl fill:#e699d9,stroke:#d94dbb,color:black
145 |     style VerifyQA fill:#e699d9,stroke:#d94dbb,color:black
146 |     
147 |     style CompleteVan fill:#8cff8c,stroke:#4dbb5f,color:black
148 |     style CompletePlan fill:#8cff8c,stroke:#4dbb5f,color:black
149 |     style CompleteCreative fill:#8cff8c,stroke:#4dbb5f,color:black
150 |     style CompleteImpl fill:#8cff8c,stroke:#4dbb5f,color:black
151 |     style CompleteQA fill:#8cff8c,stroke:#4dbb5f,color:black
152 |     
153 |     style MemoryBank fill:#f9d77e,stroke:#d9b95c,stroke-width:2px,color:black
154 |     style tasks fill:#f9d77e,stroke:#d9b95c,color:black
155 |     style projBrief fill:#f9d77e,stroke:#d9b95c,color:black
156 |     style active fill:#f9d77e,stroke:#d9b95c,color:black
157 |     style progress fill:#f9d77e,stroke:#d9b95c,color:black
158 |     
159 |     style Error fill:#ff5555,stroke:#cc0000,color:white,stroke-width:2px,color:black
160 |     style BlockCreative fill:#ffaaaa,stroke:#ff8080,color:black
161 |     style BlockMulti fill:#ffaaaa,stroke:#ff8080,color:black
162 |     style UseCorrectFn fill:#8cff8c,stroke:#4dbb5f,color:black
163 | ```
164 | 
165 | ## MEMORY BANK FILE STRUCTURE
166 | 
167 | ```mermaid
168 | flowchart TD
169 |     PB([projectbrief.md]) --> PC([productContext.md])
170 |     PB --> SP([systemPatterns.md])
171 |     PB --> TC([techContext.md])
172 |     
173 |     PC & SP & TC --> AC([activeContext.md])
174 |     
175 |     AC --> P([progress.md])
176 |     AC --> Tasks([tasks.md])
177 | 
178 |     style PB fill:#f9d77e,stroke:#d9b95c,color:black
179 |     style PC fill:#a8d5ff,stroke:#88b5e0,color:black
180 |     style SP fill:#a8d5ff,stroke:#88b5e0,color:black
181 |     style TC fill:#a8d5ff,stroke:#88b5e0,color:black
182 |     style AC fill:#c5e8b7,stroke:#a5c897,color:black
183 |     style P fill:#f4b8c4,stroke:#d498a4,color:black
184 |     style Tasks fill:#f4b8c4,stroke:#d498a4,stroke-width:3px,color:black
185 | ```
186 | 
187 | ## VERIFICATION COMMITMENT
188 | 
189 | ```
190 | ┌─────────────────────────────────────────────────────┐
191 | │ I WILL follow the appropriate visual process map    │
192 | │ I WILL run all verification checkpoints             │
193 | │ I WILL maintain tasks.md as the single source of    │
194 | │ truth for all task tracking                         │
195 | └─────────────────────────────────────────────────────┘
196 | ``` 
197 | 


--------------------------------------------------------------------------------
/isolation_rules/Core/Tools/ask-documentation-question.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: 
 3 | globs: 
 4 | alwaysApply: false
 5 | ---
 6 | ---
 7 | description: Rule for asking a specific question against existing repository documentation.
 8 | globs: ["ask-documentation-question.mdc", "*ask_question*"]
 9 | alwaysApply: false
10 | ---
11 | 
12 | # DOCUMENTATION QUESTION PROTOCOL
13 | 
14 | > **TL;DR:** This rule handles asking a single, specific question using the `ask_question` tool of deepwiki-mcp server against a repository's documentation, but ONLY if that documentation has already been retrieved and saved locally.
15 | 
16 | ## ❓ Ask Question Workflow
17 | 
18 | ```mermaid
19 | graph TD
20 |     Start["Start: User provides question and optional repo_name"] --> A{"Is documentation for this repo in ./documentation/libraries/?"};
21 |     A --> |No| B["STOP: Inform user documentation must be retrieved first using FETCHDOCS."];
22 |     A --> |Yes| C["Proceed to Ask Question"];
23 |     
24 |     C --> D["Call 'ask_question' tool with user's question and repo_name"];
25 |     D --> E["Receive answer from MCP server"];
26 |     E --> F["Format and present the answer clearly to the user."];
27 |     F --> G[END];
28 | ```
29 | 
30 | ## **Question Execution Logic:**
31 | 
32 | 1.  **PREREQUISITE CHECK:** The AI **MUST** first verify that the documentation for the relevant repository already exists in the `./documentation/libraries/` folder.
33 |     -   If the user does not specify a repository, assume the question relates to the repository most recently discussed or retrieved.
34 |     -   If the documentation folder for the repository does not exist, **STOP**. Instruct the user: "Documentation has not been retrieved for this repository yet. Please run `FETCHDOCS [URL/path]` first."
35 | 
36 | 2.  **EXECUTE QUESTION:** If the documentation exists, call the `ask_question` tool **ONCE**.
37 |     -   **Tool:** `ask_question`
38 |     -   **Parameters:**
39 |         -   `question`: The specific question provided by the user.
40 |         -   `repo_name`: The name of the repository (e.g., `a2aproject/a2a-python`).
41 | 
42 | 3.  **OUTPUT:** Present the answer returned by the tool directly to the user in a clear and readable format.
43 | 


--------------------------------------------------------------------------------
/isolation_rules/Core/command-execution.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Command execution guidelines for isolation-focused Memory Bank
  3 | globs: command-execution.mdc
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # COMMAND EXECUTION SYSTEM
  8 | 
  9 | > **TL;DR:** This system provides guidelines for efficient command execution, balancing clarity and token optimization through appropriate command chaining, with proper documentation of commands and results.
 10 | 
 11 | ## 🔍 COMMAND EFFICIENCY WORKFLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["Command<br>Planning"] --> Analyze["Analyze Command<br>Requirements"]
 16 |     Analyze --> Balance["Balance Clarity<br>vs. Efficiency"]
 17 |     Balance --> Complexity{"Command<br>Complexity?"}
 18 |     
 19 |     Complexity -->|"Simple"| Single["Execute<br>Single Command"]
 20 |     Complexity -->|"Moderate"| Chain["Use Efficient<br>Command Chaining"]
 21 |     Complexity -->|"Complex"| Group["Group Into<br>Logical Steps"]
 22 |     
 23 |     Single & Chain & Group --> Verify["Verify<br>Results"]
 24 |     Verify --> Document["Document<br>Command & Result"]
 25 |     Document --> Next["Next<br>Command"]
 26 | ```
 27 | 
 28 | ## 📋 COMMAND CHAINING GUIDELINES
 29 | 
 30 | ```mermaid
 31 | graph TD
 32 |     Command["Command<br>Execution"] --> ChainApprop{"Is Chaining<br>Appropriate?"}
 33 |     
 34 |     ChainApprop -->|"Yes"| ChainTypes["Chain<br>Types"]
 35 |     ChainApprop -->|"No"| SingleCmd["Use Single<br>Commands"]
 36 |     
 37 |     ChainTypes --> Sequential["Sequential Operations<br>cmd1 && cmd2"]
 38 |     ChainTypes --> Conditional["Conditional Operations<br>cmd1 || cmd2"]
 39 |     ChainTypes --> Piping["Piping<br>cmd1 | cmd2"]
 40 |     ChainTypes --> Grouping["Command Grouping<br>(cmd1; cmd2)"]
 41 |     
 42 |     Sequential & Conditional & Piping & Grouping --> Doc["Document<br>Commands & Results"]
 43 | ```
 44 | 
 45 | ## 🚦 DIRECTORY VERIFICATION WORKFLOW
 46 | 
 47 | ```mermaid
 48 | graph TD
 49 |     Command["Command<br>Execution"] --> DirCheck["Check Current<br>Directory"]
 50 |     DirCheck --> ProjectRoot{"In Project<br>Root?"}
 51 |     
 52 |     ProjectRoot -->|"Yes"| Execute["Execute<br>Command"]
 53 |     ProjectRoot -->|"No"| Locate["Locate<br>Project Root"]
 54 |     
 55 |     Locate --> Found{"Project Root<br>Found?"}
 56 |     Found -->|"Yes"| Navigate["Navigate to<br>Project Root"]
 57 |     Found -->|"No"| Error["Error: Cannot<br>Find Project Root"]
 58 |     
 59 |     Navigate --> Execute
 60 |     Execute --> Verify["Verify<br>Results"]
 61 | ```
 62 | 
 63 | ## 📋 DIRECTORY VERIFICATION CHECKLIST
 64 | 
 65 | Before executing any npm or build command:
 66 | 
 67 | | Step | Windows (PowerShell) | Unix/Linux/Mac | Purpose |
 68 | |------|----------------------|----------------|---------|
 69 | | **Check package.json** | `Test-Path package.json` | `ls package.json` | Verify current directory is project root |
 70 | | **Check for parent directory** | `Test-Path "*/package.json"` | `find . -maxdepth 2 -name package.json` | Find potential project directories |
 71 | | **Navigate to project root** | `cd [project-dir]` | `cd [project-dir]` | Move to correct directory before executing commands |
 72 | 
 73 | ## 📋 REACT-SPECIFIC COMMAND GUIDELINES
 74 | 
 75 | For React applications, follow these strict guidelines:
 76 | 
 77 | | Command | Correct Usage | Incorrect Usage | Notes |
 78 | |---------|---------------|----------------|-------|
 79 | | **npm start** | `cd [project-root] && npm start` | `npm start` (from parent dir) | Must execute from directory with package.json |
 80 | | **npm run build** | `cd [project-root] && npm run build` | `cd [parent-dir] && npm run build` | Must execute from directory with package.json |
 81 | | **npm install** | `cd [project-root] && npm install [pkg]` | `npm install [pkg]` (wrong dir) | Dependencies installed to nearest package.json |
 82 | | **npm create** | `npm create vite@latest my-app -- --template react` | Manually configuring webpack | Use standard tools for project creation |
 83 | 
 84 | ## 🔄 COMMAND CHAINING PATTERNS
 85 | 
 86 | Effective command chaining patterns include:
 87 | 
 88 | | Pattern | Format | Examples | Use Case |
 89 | |---------|--------|----------|----------|
 90 | | **Sequential** | `cmd1 && cmd2` | `mkdir dir && cd dir` | Commands that should run in sequence, second only if first succeeds |
 91 | | **Conditional** | `cmd1 || cmd2` | `test -f file.txt || touch file.txt` | Fallback commands, second only if first fails |
 92 | | **Piping** | `cmd1 \| cmd2` | `grep "pattern" file.txt \| wc -l` | Pass output of first command as input to second |
 93 | | **Background** | `cmd &` | `npm start &` | Run command in background |
 94 | | **Grouping** | `(cmd1; cmd2)` | `(echo "Start"; npm test; echo "End")` | Group commands to run as a unit |
 95 | 
 96 | ## 📋 COMMAND DOCUMENTATION TEMPLATE
 97 | 
 98 | ```
 99 | ## Command Execution: [Purpose]
100 | 
101 | ### Command
102 | ```
103 | [actual command or chain]
104 | ```
105 | 
106 | ### Result
107 | ```
108 | [command output]
109 | ```
110 | 
111 | ### Effect
112 | [Brief description of what changed in the system]
113 | 
114 | ### Next Steps
115 | [What needs to be done next]
116 | ```
117 | 
118 | ## 🔍 PLATFORM-SPECIFIC CONSIDERATIONS
119 | 
120 | ```mermaid
121 | graph TD
122 |     Platform["Platform<br>Detection"] --> Windows["Windows<br>Commands"]
123 |     Platform --> Unix["Unix/Linux/Mac<br>Commands"]
124 |     
125 |     Windows --> WinAdapt["Windows Command<br>Adaptations"]
126 |     Unix --> UnixAdapt["Unix Command<br>Adaptations"]
127 |     
128 |     WinAdapt --> WinChain["Windows Chaining:<br>Commands separated by &"]
129 |     UnixAdapt --> UnixChain["Unix Chaining:<br>Commands separated by ;"]
130 |     
131 |     WinChain & UnixChain --> Execute["Execute<br>Platform-Specific<br>Commands"]
132 | ```
133 | 
134 | ## 📋 COMMAND EFFICIENCY EXAMPLES
135 | 
136 | Examples of efficient command usage:
137 | 
138 | | Inefficient | Efficient | Explanation |
139 | |-------------|-----------|-------------|
140 | | `mkdir dir`<br>`cd dir`<br>`npm init -y` | `mkdir dir && cd dir && npm init -y` | Combines related sequential operations |
141 | | `ls`<br>`grep "\.js

quot;` | `ls \| grep "\.js

quot;` | Pipes output of first command to second |
142 | | `test -f file.txt`<br>`if not exists, touch file.txt` | `test -f file.txt \|\| touch file.txt` | Creates file only if it doesn't exist |
143 | | `mkdir dir1`<br>`mkdir dir2`<br>`mkdir dir3` | `mkdir dir1 dir2 dir3` | Uses command's built-in multiple argument capability |
144 | | `npm install pkg1`<br>`npm install pkg2` | `npm install pkg1 pkg2` | Installs multiple packages in one command |
145 | 
146 | ## 📋 REACT PROJECT INITIALIZATION STANDARDS
147 | 
148 | Always use these standard approaches for React project creation:
149 | 
150 | | Approach | Command | Benefits | Avoids |
151 | |----------|---------|----------|--------|
152 | | **Create React App** | `npx create-react-app my-app` | Preconfigured webpack & babel | Manual configuration errors |
153 | | **Create React App w/TypeScript** | `npx create-react-app my-app --template typescript` | Type safety + preconfigured | Inconsistent module systems |
154 | | **Vite** | `npm create vite@latest my-app -- --template react` | Faster build times | Complex webpack setups |
155 | | **Next.js** | `npx create-next-app@latest my-app` | SSR support | Module system conflicts |
156 | 
157 | ## ⚠️ ERROR HANDLING WORKFLOW
158 | 
159 | ```mermaid
160 | sequenceDiagram
161 |     participant User
162 |     participant AI
163 |     participant System
164 |     
165 |     AI->>System: Execute Command
166 |     System->>AI: Return Result
167 |     
168 |     alt Success
169 |         AI->>AI: Verify Expected Result
170 |         AI->>User: Report Success
171 |     else Error
172 |         AI->>AI: Analyze Error Message
173 |         AI->>AI: Identify Likely Cause
174 |         AI->>User: Explain Error & Cause
175 |         AI->>User: Suggest Corrective Action
176 |         User->>AI: Approve Correction
177 |         AI->>System: Execute Corrected Command
178 |     end
179 | ```
180 | 
181 | ## 📋 COMMAND RESULT VERIFICATION
182 | 
183 | After command execution, verify:
184 | 
185 | ```mermaid
186 | graph TD
187 |     Execute["Execute<br>Command"] --> Check{"Check<br>Result"}
188 |     
189 |     Check -->|"Success"| Verify["Verify Expected<br>Outcome"]
190 |     Check -->|"Error"| Analyze["Analyze<br>Error"]
191 |     
192 |     Verify -->|"Expected"| Document["Document<br>Success"]
193 |     Verify -->|"Unexpected"| Investigate["Investigate<br>Unexpected Result"]
194 |     
195 |     Analyze --> Diagnose["Diagnose<br>Error Cause"]
196 |     Diagnose --> Correct["Propose<br>Correction"]
197 |     
198 |     Document & Investigate & Correct --> Next["Next Step<br>in Process"]
199 | ```
200 | 
201 | ## 📝 COMMAND EXECUTION CHECKLIST
202 | 
203 | ```
204 | ✓ COMMAND EXECUTION CHECKLIST
205 | - Command purpose clearly identified? [YES/NO]
206 | - Appropriate balance of clarity vs. efficiency? [YES/NO]
207 | - Platform-specific considerations addressed? [YES/NO]
208 | - Command documented with results? [YES/NO]
209 | - Outcome verified against expectations? [YES/NO]
210 | - Errors properly handled (if any)? [YES/NO/NA]
211 | - For npm/build commands: Executed from project root? [YES/NO/NA]
212 | - For React projects: Using standard tooling? [YES/NO/NA]
213 | 
214 | → If all YES: Command execution complete
215 | → If any NO: Address missing elements
216 | ```
217 | 
218 | ## 🚨 COMMAND EXECUTION WARNINGS
219 | 
220 | Avoid these common command issues:
221 | 
222 | ```mermaid
223 | graph TD
224 |     Warning["Command<br>Warnings"] --> W1["Excessive<br>Verbosity"]
225 |     Warning --> W2["Insufficient<br>Error Handling"]
226 |     Warning --> W3["Unnecessary<br>Complexity"]
227 |     Warning --> W4["Destructive<br>Operations Without<br>Confirmation"]
228 |     Warning --> W5["Wrong Directory<br>Execution"]
229 |     
230 |     W1 --> S1["Use flags to reduce<br>unnecessary output"]
231 |     W2 --> S2["Include error handling<br>in command chains"]
232 |     W3 --> S3["Prefer built-in<br>command capabilities"]
233 |     W4 --> S4["Show confirmation<br>before destructive actions"]
234 |     W5 --> S5["Verify directory before<br>npm/build commands"]
235 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Core/complexity-decision-tree.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: complexity decision tree
  3 | globs: complexity-decision-tree.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # TASK COMPLEXITY DETERMINATION
  7 | 
  8 | > **TL;DR:** This document helps determine the appropriate complexity level (1-4) for any task. Use the decision tree and indicators to select the right process level, then load the corresponding process map.
  9 | 
 10 | ## 🌳 COMPLEXITY DECISION TREE
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["New Task"] --> Q1{"Bug fix or<br>error correction?"}
 15 |     Q1 -->|Yes| Q1a{"Affects single<br>component?"}
 16 |     Q1a -->|Yes| L1["Level 1:<br>Quick Bug Fix"]
 17 |     Q1a -->|No| Q1b{"Affects multiple<br>components?"}
 18 |     Q1b -->|Yes| L2["Level 2:<br>Simple Enhancement"]
 19 |     Q1b -->|No| Q1c{"Affects system<br>architecture?"}
 20 |     Q1c -->|Yes| L3["Level 3:<br>Intermediate Feature"]
 21 |     Q1c -->|No| L2
 22 |     
 23 |     Q1 -->|No| Q2{"Adding small<br>feature or<br>enhancement?"}
 24 |     Q2 -->|Yes| Q2a{"Self-contained<br>change?"}
 25 |     Q2a -->|Yes| L2
 26 |     Q2a -->|No| Q2b{"Affects multiple<br>components?"}
 27 |     Q2b -->|Yes| L3
 28 |     Q2b -->|No| L2
 29 |     
 30 |     Q2 -->|No| Q3{"Complete feature<br>requiring multiple<br>components?"}
 31 |     Q3 -->|Yes| Q3a{"Architectural<br>implications?"}
 32 |     Q3a -->|Yes| L4["Level 4:<br>Complex System"]
 33 |     Q3a -->|No| L3
 34 |     
 35 |     Q3 -->|No| Q4{"System-wide or<br>architectural<br>change?"}
 36 |     Q4 -->|Yes| L4
 37 |     Q4 -->|No| L3
 38 |     
 39 |     L1 --> LoadL1["Load Level 1 Map"]
 40 |     L2 --> LoadL2["Load Level 2 Map"]
 41 |     L3 --> LoadL3["Load Level 3 Map"]
 42 |     L4 --> LoadL4["Load Level 4 Map"]
 43 | ```
 44 | 
 45 | ## 📊 COMPLEXITY LEVEL INDICATORS
 46 | 
 47 | Use these indicators to help determine task complexity:
 48 | 
 49 | ### Level 1: Quick Bug Fix
 50 | - **Keywords**: "fix", "broken", "not working", "issue", "bug", "error", "crash"
 51 | - **Scope**: Single component or UI element
 52 | - **Duration**: Can be completed quickly (minutes to hours)
 53 | - **Risk**: Low, isolated changes
 54 | - **Examples**:
 55 |   - Fix button not working
 56 |   - Correct styling issue
 57 |   - Fix validation error
 58 |   - Resolve broken link
 59 |   - Fix typo or text issue
 60 | 
 61 | ### Level 2: Simple Enhancement
 62 | - **Keywords**: "add", "improve", "update", "change", "enhance", "modify"
 63 | - **Scope**: Single component or subsystem
 64 | - **Duration**: Hours to 1-2 days
 65 | - **Risk**: Moderate, contained to specific area
 66 | - **Examples**:
 67 |   - Add form field
 68 |   - Improve validation
 69 |   - Update styling
 70 |   - Add simple feature
 71 |   - Change text content
 72 |   - Enhance existing component
 73 | 
 74 | ### Level 3: Intermediate Feature
 75 | - **Keywords**: "implement", "create", "develop", "build", "feature"
 76 | - **Scope**: Multiple components, complete feature
 77 | - **Duration**: Days to 1-2 weeks
 78 | - **Risk**: Significant, affects multiple areas
 79 | - **Examples**:
 80 |   - Implement user authentication
 81 |   - Create dashboard
 82 |   - Develop search functionality
 83 |   - Build user profile system
 84 |   - Implement data visualization
 85 |   - Create complex form system
 86 | 
 87 | ### Level 4: Complex System
 88 | - **Keywords**: "system", "architecture", "redesign", "integration", "framework"
 89 | - **Scope**: Multiple subsystems or entire application
 90 | - **Duration**: Weeks to months
 91 | - **Risk**: High, architectural implications
 92 | - **Examples**:
 93 |   - Implement authentication system
 94 |   - Build payment processing framework
 95 |   - Create microservice architecture
 96 |   - Implement database migration system
 97 |   - Develop real-time communication system
 98 |   - Create multi-tenant architecture
 99 | 
100 | ## 🔍 COMPLEXITY ASSESSMENT QUESTIONS
101 | 
102 | Answer these questions to determine complexity:
103 | 
104 | 1. **Scope Impact**
105 |    - Does it affect a single component or multiple?
106 |    - Are there system-wide implications?
107 |    - How many files will need to be modified?
108 | 
109 | 2. **Design Decisions**
110 |    - Are complex design decisions required?
111 |    - Will it require creative phases for design?
112 |    - Are there architectural considerations?
113 | 
114 | 3. **Risk Assessment**
115 |    - What happens if it fails?
116 |    - Are there security implications?
117 |    - Will it affect critical functionality?
118 | 
119 | 4. **Implementation Effort**
120 |    - How long will it take to implement?
121 |    - Does it require specialized knowledge?
122 |    - Is extensive testing needed?
123 | 
124 | ## 📊 KEYWORD ANALYSIS TABLE
125 | 
126 | | Keyword | Likely Level | Notes |
127 | |---------|--------------|-------|
128 | | "Fix" | Level 1 | Unless system-wide |
129 | | "Bug" | Level 1 | Unless multiple components |
130 | | "Error" | Level 1 | Unless architectural |
131 | | "Add" | Level 2 | Unless complex feature |
132 | | "Update" | Level 2 | Unless architectural |
133 | | "Improve" | Level 2 | Unless system-wide |
134 | | "Implement" | Level 3 | Complex components |
135 | | "Create" | Level 3 | New functionality |
136 | | "Develop" | Level 3 | Significant scope |
137 | | "System" | Level 4 | Architectural implications |
138 | | "Architecture" | Level 4 | Major structural changes |
139 | | "Framework" | Level 4 | Core infrastructure |
140 | 
141 | ## 🔄 COMPLEXITY ESCALATION
142 | 
143 | If during a task you discover it's more complex than initially determined:
144 | 
145 | ```
146 | ⚠️ TASK ESCALATION NEEDED
147 | Current Level: Level [X]
148 | Recommended Level: Level [Y]
149 | Reason: [Brief explanation]
150 | 
151 | Would you like me to escalate this task to Level [Y]?
152 | ```
153 | 
154 | If approved, switch to the appropriate higher-level process map.
155 | 
156 | ## 🎯 PROCESS SELECTION
157 | 
158 | After determining complexity, load the appropriate process map:
159 | 
160 | | Level | Description | Process Map |
161 | |-------|-------------|-------------|
162 | | 1 | Quick Bug Fix | [Level 1 Map](mdc:.cursor/rules/visual-maps/level1-map.mdc) |
163 | | 2 | Simple Enhancement | [Level 2 Map](mdc:.cursor/rules/visual-maps/level2-map.mdc) |
164 | | 3 | Intermediate Feature | [Level 3 Map](mdc:.cursor/rules/visual-maps/level3-map.mdc) |
165 | | 4 | Complex System | [Level 4 Map](mdc:.cursor/rules/visual-maps/level4-map.mdc) |
166 | 
167 | ## 📝 COMPLEXITY DETERMINATION TEMPLATE
168 | 
169 | Use this template to document complexity determination:
170 | 
171 | ```
172 | ## COMPLEXITY DETERMINATION
173 | 
174 | Task: [Task description]
175 | 
176 | Assessment:
177 | - Scope: [Single component/Multiple components/System-wide]
178 | - Design decisions: [Simple/Moderate/Complex]
179 | - Risk: [Low/Moderate/High]
180 | - Implementation effort: [Low/Moderate/High]
181 | 
182 | Keywords identified: [List relevant keywords]
183 | 
184 | Determination: Level [1/2/3/4] - [Quick Bug Fix/Simple Enhancement/Intermediate Feature/Complex System]
185 | 
186 | Loading process map: [Level X Map]
187 | ```
188 | 


--------------------------------------------------------------------------------
/isolation_rules/Core/creative-phase-enforcement.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: creative phase enforcement 
  3 | globs: creative-phase-enforcement.md
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # CREATIVE PHASE ENFORCEMENT
  8 | 
  9 | > **TL;DR:** This document implements strict enforcement of creative phase requirements for Level 3-4 tasks, ensuring all design decisions are properly documented and verified before implementation can proceed.
 10 | 
 11 | ## 🔍 ENFORCEMENT WORKFLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["Task Start"] --> Check{"Level 3-4<br>Task?"}
 16 |     Check -->|Yes| Analyze["Analyze Design<br>Decision Points"]
 17 |     Check -->|No| Optional["Creative Phase<br>Optional"]
 18 |     
 19 |     Analyze --> Decision{"Design Decisions<br>Required?"}
 20 |     Decision -->|Yes| Gate["🚨 IMPLEMENTATION<br>BLOCKED"]
 21 |     Decision -->|No| Allow["Allow<br>Implementation"]
 22 |     
 23 |     Gate --> Creative["Enter Creative<br>Phase"]
 24 |     Creative --> Verify{"All Decisions<br>Documented?"}
 25 |     Verify -->|No| Return["Return to<br>Creative Phase"]
 26 |     Verify -->|Yes| Proceed["Allow<br>Implementation"]
 27 | 
 28 | ```
 29 | 
 30 | ## 🚨 ENFORCEMENT GATES
 31 | 
 32 | ```mermaid
 33 | graph TD
 34 |     subgraph "CREATIVE PHASE GATES"
 35 |     G1["Entry Gate<br>Verify Requirements"]
 36 |     G2["Process Gate<br>Verify Progress"]
 37 |     G3["Exit Gate<br>Verify Completion"]
 38 |     end
 39 |     G1 --> G2 --> G3
 40 | ```
 41 | 
 42 | ## 📋 ENFORCEMENT CHECKLIST
 43 | 
 44 | ```markdown
 45 | ## Entry Gate Verification
 46 | - [ ] Task complexity is Level 3-4
 47 | - [ ] Design decisions identified
 48 | - [ ] Creative phase requirements documented
 49 | - [ ] Required participants notified
 50 | 
 51 | ## Process Gate Verification
 52 | - [ ] All options being considered
 53 | - [ ] Pros/cons documented
 54 | - [ ] Technical constraints identified
 55 | - [ ] Implementation impacts assessed
 56 | 
 57 | ## Exit Gate Verification
 58 | - [ ] All decisions documented
 59 | - [ ] Rationale provided for choices
 60 | - [ ] Implementation plan outlined
 61 | - [ ] Verification against requirements
 62 | ```
 63 | 
 64 | ## 🚨 IMPLEMENTATION BLOCK NOTICE
 65 | 
 66 | When a creative phase is required but not completed:
 67 | 
 68 | ```
 69 | 🚨 IMPLEMENTATION BLOCKED
 70 | Creative phases MUST be completed before implementation.
 71 | 
 72 | Required Creative Phases:
 73 | - [ ] [Creative Phase 1]
 74 | - [ ] [Creative Phase 2]
 75 | - [ ] [Creative Phase 3]
 76 | 
 77 | ⛔ This is a HARD BLOCK
 78 | Implementation CANNOT proceed until all creative phases are completed.
 79 | Type "PHASE.REVIEW" to begin creative phase review.
 80 | ```
 81 | 
 82 | ## ✅ VERIFICATION PROTOCOL
 83 | 
 84 | ```mermaid
 85 | graph TD
 86 |     subgraph "VERIFICATION STEPS"
 87 |     V1["1. Requirements<br>Check"]
 88 |     V2["2. Documentation<br>Review"]
 89 |     V3["3. Decision<br>Validation"]
 90 |     V4["4. Implementation<br>Readiness"]
 91 |     end
 92 |     
 93 |     V1 --> V2 --> V3 --> V4
 94 | ```
 95 | 
 96 | ## 🔄 CREATIVE PHASE MARKERS
 97 | 
 98 | Use these markers to clearly indicate creative phase boundaries:
 99 | 
100 | ```markdown
101 | 🎨🎨🎨 ENTERING CREATIVE PHASE: [TYPE] 🎨🎨🎨
102 | Focus: [Specific component/feature]
103 | Objective: [Clear goal of this creative phase]
104 | Requirements: [List of requirements]
105 | 
106 | [Creative phase content]
107 | 
108 | 🎨 CREATIVE CHECKPOINT: [Milestone]
109 | - Progress: [Status]
110 | - Decisions: [List]
111 | - Next steps: [Plan]
112 | 
113 | 🎨🎨🎨 EXITING CREATIVE PHASE 🎨🎨🎨
114 | Summary: [Brief description]
115 | Key Decisions: [List]
116 | Next Steps: [Implementation plan]
117 | ```
118 | 
119 | ## 🔄 DOCUMENT MANAGEMENT
120 | 
121 | ```mermaid
122 | graph TD
123 |     Current["Current Document"] --> Active["Active:<br>- creative-phase-enforcement.md"]
124 |     Current --> Related["Related:<br>- creative-phase-architecture.md<br>- task-tracking-intermediate.md"]
125 |  ``` 


--------------------------------------------------------------------------------
/isolation_rules/Core/creative-phase-metrics.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: creative phase metrics
  3 | globs: creative-phase-metrics.md
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | 
  8 | 
  9 | # CREATIVE PHASE METRICS
 10 | 
 11 | > **TL;DR:** This document defines comprehensive quality metrics and measurement criteria for creative phases, ensuring that design decisions meet required standards and are properly documented.
 12 | 
 13 | ## 📊 METRICS OVERVIEW
 14 | 
 15 | ```mermaid
 16 | graph TD
 17 |     subgraph "CREATIVE PHASE METRICS"
 18 |     M1["Documentation<br>Quality"]
 19 |     M2["Decision<br>Coverage"]
 20 |     M3["Option<br>Analysis"]
 21 |     M4["Impact<br>Assessment"]
 22 |     M5["Verification<br>Score"]
 23 |     end
 24 |     
 25 |     M1 --> Score["Quality<br>Score"]
 26 |     M2 --> Score
 27 |     M3 --> Score
 28 |     M4 --> Score
 29 |     M5 --> Score
 30 | ```
 31 | 
 32 | ## 📋 QUALITY METRICS SCORECARD
 33 | 
 34 | ```markdown
 35 | # Creative Phase Quality Assessment
 36 | 
 37 | ## 1. Documentation Quality [0-10]
 38 | - [ ] Clear problem statement (2 points)
 39 | - [ ] Well-defined objectives (2 points)
 40 | - [ ] Comprehensive requirements list (2 points)
 41 | - [ ] Proper formatting and structure (2 points)
 42 | - [ ] Cross-references to related documents (2 points)
 43 | 
 44 | ## 2. Decision Coverage [0-10]
 45 | - [ ] All required decisions identified (2 points)
 46 | - [ ] Each decision point documented (2 points)
 47 | - [ ] Dependencies mapped (2 points)
 48 | - [ ] Impact analysis included (2 points)
 49 | - [ ] Future considerations noted (2 points)
 50 | 
 51 | ## 3. Option Analysis [0-10]
 52 | - [ ] Multiple options considered (2 points)
 53 | - [ ] Pros/cons documented (2 points)
 54 | - [ ] Technical feasibility assessed (2 points)
 55 | - [ ] Resource requirements estimated (2 points)
 56 | - [ ] Risk factors identified (2 points)
 57 | 
 58 | ## 4. Impact Assessment [0-10]
 59 | - [ ] System impact documented (2 points)
 60 | - [ ] Performance implications assessed (2 points)
 61 | - [ ] Security considerations addressed (2 points)
 62 | - [ ] Maintenance impact evaluated (2 points)
 63 | - [ ] Cost implications analyzed (2 points)
 64 | 
 65 | ## 5. Verification Score [0-10]
 66 | - [ ] Requirements traced (2 points)
 67 | - [ ] Constraints validated (2 points)
 68 | - [ ] Test scenarios defined (2 points)
 69 | - [ ] Review feedback incorporated (2 points)
 70 | - [ ] Final verification completed (2 points)
 71 | 
 72 | Total Score: [Sum of all categories] / 50
 73 | Minimum Required Score: 40/50 (80%)
 74 | ```
 75 | 
 76 | ## 📈 QUALITY THRESHOLDS
 77 | 
 78 | ```mermaid
 79 | graph TD
 80 |     subgraph "QUALITY GATES"
 81 |     T1["Minimum<br>40/50 (80%)"]
 82 |     T2["Target<br>45/50 (90%)"]
 83 |     T3["Excellent<br>48/50 (96%)"]
 84 |     end
 85 |     
 86 |     Score["Quality<br>Score"] --> Check{"Meets<br>Threshold?"}
 87 |     Check -->|"< 80%"| Block["⛔ BLOCKED<br>Improvements Required"]
 88 |     Check -->|"≥ 80%"| Pass["✓ PASSED<br>Can Proceed"]
 89 | ```
 90 | 
 91 | ## 🎯 METRIC EVALUATION PROCESS
 92 | 
 93 | ```mermaid
 94 | graph TD
 95 |     Start["Start<br>Evaluation"] --> Doc["1. Score<br>Documentation"]
 96 |     Doc --> Dec["2. Assess<br>Decisions"]
 97 |     Dec --> Opt["3. Review<br>Options"]
 98 |     Opt --> Imp["4. Evaluate<br>Impact"]
 99 |     Imp --> Ver["5. Verify<br>Completeness"]
100 |     Ver --> Total["Calculate<br>Total Score"]
101 |     Total --> Check{"Meets<br>Threshold?"}
102 |     Check -->|No| Return["Return for<br>Improvements"]
103 |     Check -->|Yes| Proceed["Proceed to<br>Next Phase"]
104 | ```
105 | 
106 | ## 📊 IMPROVEMENT RECOMMENDATIONS
107 | 
108 | For scores below threshold:
109 | 
110 | ```markdown
111 | ## Documentation Quality Improvements
112 | - Add clear problem statements
113 | - Include specific objectives
114 | - List all requirements
115 | - Improve formatting
116 | - Add cross-references
117 | 
118 | ## Decision Coverage Improvements
119 | - Identify missing decisions
120 | - Document all decision points
121 | - Map dependencies
122 | - Add impact analysis
123 | - Consider future implications
124 | 
125 | ## Option Analysis Improvements
126 | - Consider more alternatives
127 | - Detail pros/cons
128 | - Assess technical feasibility
129 | - Estimate resource needs
130 | - Identify risks
131 | 
132 | ## Impact Assessment Improvements
133 | - Document system impact
134 | - Assess performance
135 | - Address security
136 | - Evaluate maintenance
137 | - Analyze costs
138 | 
139 | ## Verification Improvements
140 | - Trace requirements
141 | - Validate constraints
142 | - Define test scenarios
143 | - Incorporate feedback
144 | - Complete verification
145 | ```
146 | 
147 | ## ✅ METRICS VERIFICATION CHECKLIST
148 | 
149 | ```markdown
150 | ## Pre-Review Verification
151 | - [ ] All sections scored
152 | - [ ] Calculations verified
153 | - [ ] Supporting evidence attached
154 | - [ ] Improvement areas identified
155 | - [ ] Review feedback incorporated
156 | 
157 | ## Final Metrics Verification
158 | - [ ] Minimum score achieved
159 | - [ ] All categories passed
160 | - [ ] Documentation complete
161 | - [ ] Improvements addressed
162 | - [ ] Final approval obtained
163 | ```
164 | 
165 | ## 🔄 DOCUMENT MANAGEMENT
166 | 
167 | ```mermaid
168 | graph TD
169 |     Current["Current Document"] --> Active["Active:<br>- creative-phase-metrics.md"]
170 |     Current --> Related["Related:<br>- creative-phase-enforcement.md<br>- creative-phase-architecture.md"]
171 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Core/documentation-retrieval.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: 
 3 | globs: 
 4 | alwaysApply: false
 5 | ---
 6 | ---
 7 | description: Rule for retrieving and saving documentation from repositories.
 8 | globs: ["documentation-retrieval.mdc", "*docs*", "*documentation*"]
 9 | alwaysApply: false
10 | ---
11 | 
12 | # DOCUMENTATION RETRIEVAL & SAVING PROTOCOL
13 | 
14 | > **TL;DR:** This rule defines a strict, one-time process for fetching repository documentation from sources like GitHub/DeepWiki with deepwiki-mcp server, saving it locally to `./documentation/libraries/`, and preventing duplicate retrievals within the same conversation.
15 | 
16 | ## ⚙️ Documentation Retrieval Workflow
17 | 
18 | ```mermaid
19 | graph TD
20 |     subgraph "Input Analysis"
21 |         A[Start: User requests documentation for URL/repo] --> B{"URL or Path provided?"};
22 |         B --> |URL| C{"URL contains 'github.com'?"};
23 |         B --> |Path| E[Proceed with Repository Path];
24 |         C --> |Yes| D["Convert to deepwiki format"];
25 |         C --> |No| E;
26 |         D --> E;
27 |     end
28 | 
29 |     subgraph "Pre-flight Checks"
30 |         E --> F{"Already retrieved in this conversation?"};
31 |         F --> |Yes| Stop1["STOP: Say 'Documentation already retrieved'"];
32 |         F --> |No| G{"Docs exist in ./documentation/libraries/?"};
33 |         G --> |Yes| Stop2["STOP: Say 'Documentation already retrieved'"];
34 |         G --> |No| H[Proceed to Execution];
35 |     end
36 | 
37 |     subgraph "Execution & Saving (ONCE PER REPO)"
38 |         H --> I["1. Call read_wiki_structure"];
39 |         I --> J["2. IMMEDIATELY Save to {repo}_structure.md"];
40 |         J --> K["3. Call read_wiki_contents"];
41 |         K --> L["4. IMMEDIATELY Save to {repo}_content.md"];
42 |         L --> M["5. Create combined {repo}_complete_documentation.md"];
43 |         M --> N["6. Output: '✅ DOCUMENTATION SAVED'"];
44 |     end
45 |     
46 |     subgraph "Final Output"
47 |         N --> O["Respond to user with file location and summary"];
48 |         O --> P[END];
49 |     end
50 | ```
51 | 
52 | ## **Documentation Retrieval Logic:**
53 | 
54 | -   **FIRST CHECK:** If documentation for this repository was already retrieved in this conversation, OR its documentation is already in the `./documentation/libraries/` folder, **DO NOT proceed**. Say "Documentation already retrieved for this repository."
55 | -   If the URL contains "github.com": Convert it to the deepwiki format (e.g., `https://github.com/a2aproject/a2a-python` -> `https://deepwiki.com/a2aproject/a2a-python`).
56 | -   If the URL contains "deepwiki.com" OR the user provides a repository path: Proceed directly with available tools: `read_wiki_structure`, `read_wiki_contents`, `ask_question`.
57 | 
58 | ## **EXECUTE EXACTLY ONCE PER REPOSITORY:**
59 | 
60 | 1.  Check if this repository has already been processed in the current session. If YES, stop immediately.
61 | 2.  Call `read_wiki_structure` **ONCE**.
62 | 3.  **IMMEDIATELY** after `read_wiki_structure` returns, save its structure to a file: `./documentation/libraries/{repo_name}_structure.md`.
63 | 4.  Call `read_wiki_contents` **ONCE**.
64 | 5.  **IMMEDIATELY** after `read_wiki_contents` returns, save its content to a file: `./documentation/libraries/{repo_name}_content.md` (DO NOT wait, save RIGHT AWAY).
65 | 6.  Create a combined documentation file: `./documentation/libraries/{repo_name}_complete_documentation.md`.
66 | 7.  Output the final confirmation message: "✅ DOCUMENTATION SAVED TO FILES - RULE EXECUTION FINISHED".
67 | 8.  **DO NOT** call these functions again for the same repository in this conversation.
68 | 
69 | **CRITICAL: Save content to files IMMEDIATELY after each function call to prevent context overflow and potential agent resets.**
70 | 
71 | ## **After Completion:**
72 | 
73 | -   Respond to the user with the location of the saved files and a brief summary of the retrieved documentation.


--------------------------------------------------------------------------------
/isolation_rules/Core/file-verification.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Optimized file verification
  3 | globs: file-verification.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # OPTIMIZED FILE VERIFICATION SYSTEM
  7 | 
  8 | > **TL;DR:** This system efficiently verifies and creates required Memory Bank file structures using batch operations and platform-optimized commands.
  9 | 
 10 | ## 🔍 OPTIMIZED FILE VERIFICATION WORKFLOW
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["Start File<br>Verification"] --> VerifyAll["Verify All<br>Required Components"]
 15 |     VerifyAll --> MissingCheck{"Missing<br>Components?"}
 16 |     MissingCheck -->|"Yes"| BatchCreate["Batch Create<br>All Missing Items"]
 17 |     MissingCheck -->|"No"| Complete["Verification<br>Complete"]
 18 |     BatchCreate --> Report["Generate<br>Verification Report"]
 19 |     Report --> Complete
 20 | ```
 21 | 
 22 | ## 📋 OPTIMIZED DIRECTORY CREATION
 23 | 
 24 | ```mermaid
 25 | graph TD
 26 |     Start["Directory<br>Creation"] --> DetectOS["Detect Operating<br>System"]
 27 |     DetectOS -->|"Windows"| WinCmd["Batch Create<br>Windows Command"]
 28 |     DetectOS -->|"Mac/Linux"| UnixCmd["Batch Create<br>Unix Command"]
 29 |     WinCmd & UnixCmd --> Verify["Verify<br>Creation Success"]
 30 |     Verify --> Complete["Directory Setup<br>Complete"]
 31 | ```
 32 | 
 33 | ### Platform-Specific Commands
 34 | 
 35 | #### Windows (PowerShell)
 36 | ```powershell
 37 | # Create all directories in one command
 38 | mkdir documentation\memory-bank, docs, docs\archive -ErrorAction SilentlyContinue
 39 | 
 40 | # Create all required files
 41 | $files = @(".cursorrules", "tasks.md", 
 42 |            "documentation\memory-bank\projectbrief.md", 
 43 |            "documentation\memory-bank\productContext.md",
 44 |            "documentation\memory-bank\systemPatterns.md",
 45 |            "documentation\memory-bank\techContext.md",
 46 |            "documentation\memory-bank\activeContext.md",
 47 |            "documentation\memory-bank\progress.md")
 48 | 
 49 | foreach ($file in $files) {
 50 |     if (-not (Test-Path $file)) {
 51 |         New-Item -Path $file -ItemType File -Force
 52 |     }
 53 | }
 54 | ```
 55 | 
 56 | #### Mac/Linux (Bash)
 57 | ```bash
 58 | # Create all directories in one command
 59 | mkdir -p documentation\memory-bank docs/archive
 60 | 
 61 | # Create all required files
 62 | touch .cursorrules tasks.md \
 63 |       documentation\memory-bank/projectbrief.md \
 64 |       documentation\memory-bank/productContext.md \
 65 |       documentation\memory-bank/systemPatterns.md \
 66 |       documentation\memory-bank/techContext.md \
 67 |       documentation\memory-bank/activeContext.md \
 68 |       documentation\memory-bank/progress.md
 69 | ```
 70 | 
 71 | ## 📝 STREAMLINED VERIFICATION PROCESS
 72 | 
 73 | Instead of checking each component separately, perform batch verification:
 74 | 
 75 | ```powershell
 76 | # Windows - PowerShell
 77 | $requiredDirs = @("documentation\memory-bank", "docs", "docs\archive")
 78 | $requiredFiles = @(".cursorrules", "tasks.md")
 79 | $mbFiles = @("projectbrief.md", "productContext.md", "systemPatterns.md", 
 80 |              "techContext.md", "activeContext.md", "progress.md")
 81 | 
 82 | $missingDirs = $requiredDirs | Where-Object { -not (Test-Path $_) -or -not (Test-Path $_ -PathType Container) }
 83 | $missingFiles = $requiredFiles | Where-Object { -not (Test-Path $_) -or (Test-Path $_ -PathType Container) }
 84 | $missingMBFiles = $mbFiles | ForEach-Object { "documentation\memory-bank\$_" } | 
 85 |                   Where-Object { -not (Test-Path $_) -or (Test-Path $_ -PathType Container) }
 86 | 
 87 | if ($missingDirs.Count -eq 0 -and $missingFiles.Count -eq 0 -and $missingMBFiles.Count -eq 0) {
 88 |     Write-Output "✓ All required components verified"
 89 | } else {
 90 |     # Create all missing items at once
 91 |     if ($missingDirs.Count -gt 0) {
 92 |         $missingDirs | ForEach-Object { mkdir $_ -Force }
 93 |     }
 94 |     if ($missingFiles.Count -gt 0 -or $missingMBFiles.Count -gt 0) {
 95 |         $allMissingFiles = $missingFiles + $missingMBFiles
 96 |         $allMissingFiles | ForEach-Object { New-Item -Path $_ -ItemType File -Force }
 97 |     }
 98 | }
 99 | ```
100 | 
101 | ## 📝 TEMPLATE INITIALIZATION
102 | 
103 | Optimize template creation with a single script:
104 | 
105 | ```powershell
106 | # Windows - PowerShell
107 | $templates = @{
108 |     "tasks.md" = @"
109 | # Memory Bank: Tasks
110 | 
111 | ## Current Task
112 | [Task not yet defined]
113 | 
114 | ## Status
115 | - [ ] Task definition
116 | - [ ] Implementation plan
117 | - [ ] Execution
118 | - [ ] Documentation
119 | 
120 | ## Requirements
121 | [No requirements defined yet]
122 | "@
123 | 
124 |     "documentation\memory-bank\activeContext.md" = @"
125 | # Memory Bank: Active Context
126 | 
127 | ## Current Focus
128 | [No active focus defined]
129 | 
130 | ## Status
131 | [No status defined]
132 | 
133 | ## Latest Changes
134 | [No changes recorded]
135 | "@
136 | 
137 |     # Add other templates here
138 | }
139 | 
140 | foreach ($file in $templates.Keys) {
141 |     if (Test-Path $file) {
142 |         Set-Content -Path $file -Value $templates[$file]
143 |     }
144 | }
145 | ```
146 | 
147 | ## 🔍 PERFORMANCE OPTIMIZATION BEST PRACTICES
148 | 
149 | 1. **Batch Operations**: Always use batch operations instead of individual commands
150 |    ```
151 |    # GOOD: Create all directories at once
152 |    mkdir documentation\memory-bank docs docs\archive
153 |    
154 |    # BAD: Create directories one at a time
155 |    mkdir documentation\memory-bank
156 |    mkdir docs
157 |    mkdir docs\archive
158 |    ```
159 | 
160 | 2. **Pre-Check Optimization**: Check all requirements first, then create only what's missing
161 |    ```
162 |    # First check what's missing
163 |    $missingItems = ...
164 |    
165 |    # Then create only what's missing
166 |    if ($missingItems) { ... }
167 |    ```
168 | 
169 | 3. **Error Handling**: Include error handling in all commands
170 |    ```
171 |    mkdir documentation\memory-bank, docs, docs\archive -ErrorAction SilentlyContinue
172 |    ```
173 | 
174 | 4. **Platform Adaptation**: Auto-detect platform and use appropriate commands
175 |    ```
176 |    if ($IsWindows) {
177 |        # Windows commands
178 |    } else {
179 |        # Unix commands
180 |    }
181 |    ```
182 | 
183 | 5. **One-Pass Verification**: Verify directory structure in a single pass
184 |    ```
185 |    $requiredPaths = @("documentation\memory-bank", "docs", "docs\archive", ".cursorrules", "tasks.md")
186 |    $missingPaths = $requiredPaths | Where-Object { -not (Test-Path $_) }
187 |    ```
188 | 
189 | ## 📝 VERIFICATION REPORT FORMAT
190 | 
191 | ```
192 | ✅ VERIFICATION COMPLETE
193 | - Created directories: [list]
194 | - Created files: [list]
195 | - All components verified
196 | 
197 | Memory Bank system ready for use.
198 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Core/hierarchical-rule-loading.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Hierarchical rule loading system for optimized token usage
  3 | globs: "**/rule-loading*/**", "**/optimization*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # HIERARCHICAL RULE LOADING SYSTEM
  8 | 
  9 | > **TL;DR:** This rule implements an optimized loading system that only loads necessary rules based on context, complexity level, and current phase to maximize token efficiency.
 10 | 
 11 | ## 🧠 HIERARCHICAL RULE STRUCTURE
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Root["Root Rules"] --> Core["Core Rules<br>(Always Loaded)"]
 16 |     Root --> Common["Common Rules<br>(Mode Independent)"]
 17 |     Root --> Mode["Mode-Specific<br>Rules"]
 18 |     Root --> Level["Complexity Level<br>Rules"]
 19 |     
 20 |     Core --> Platform["Platform<br>Detection"]
 21 |     Core --> File["File<br>Operations"]
 22 |     Core --> Transition["Mode<br>Transitions"]
 23 |     
 24 |     Mode --> VAN["VAN Mode<br>Rules"]
 25 |     Mode --> PLAN["PLAN Mode<br>Rules"]
 26 |     Mode --> CREATIVE["CREATIVE Mode<br>Rules"]
 27 |     Mode --> IMPLEMENT["IMPLEMENT Mode<br>Rules"]
 28 |     Mode --> REFLECT["REFLECT Mode<br>Rules"]
 29 |     
 30 |     Level --> Level1["Level 1<br>Rules"]
 31 |     Level --> Level2["Level 2<br>Rules"]
 32 |     Level --> Level3["Level 3<br>Rules"]
 33 |     Level --> Level4["Level 4<br>Rules"]
 34 | ```
 35 | 
 36 | ## 📊 RULE LOADING PROTOCOL
 37 | 
 38 | ```mermaid
 39 | sequenceDiagram
 40 |     participant User
 41 |     participant LoadManager
 42 |     participant RuleCache
 43 |     participant FileSystem
 44 |     
 45 |     User->>LoadManager: Request mode activation
 46 |     LoadManager->>RuleCache: Check cached core rules
 47 |     RuleCache-->>LoadManager: Return cached rules if available
 48 |     
 49 |     LoadManager->>FileSystem: Load essential mode rules
 50 |     FileSystem-->>LoadManager: Return essential rules
 51 |     
 52 |     LoadManager->>LoadManager: Register lazy loaders for specialized rules
 53 |     LoadManager->>User: Return initialized mode
 54 |     
 55 |     User->>LoadManager: Request specialized functionality
 56 |     LoadManager->>RuleCache: Check specialized rule cache
 57 |     RuleCache-->>LoadManager: Return cached rule if available
 58 |     
 59 |     alt Rule not in cache
 60 |         LoadManager->>FileSystem: Load specialized rule
 61 |         FileSystem-->>LoadManager: Return specialized rule
 62 |         LoadManager->>RuleCache: Cache specialized rule
 63 |     end
 64 |     
 65 |     LoadManager->>User: Execute specialized functionality
 66 | ```
 67 | 
 68 | ## 🔄 RULE LOADING IMPLEMENTATION
 69 | 
 70 | ```javascript
 71 | // Pseudocode for hierarchical rule loading
 72 | class RuleLoadManager {
 73 |   constructor() {
 74 |     this.cache = {
 75 |       core: {},
 76 |       common: {},
 77 |       mode: {},
 78 |       level: {}
 79 |     };
 80 |     this.lazyLoaders = {};
 81 |   }
 82 |   
 83 |   // Initialize a mode with only essential rules
 84 |   initializeMode(modeName, complexityLevel) {
 85 |     // Always load core rules
 86 |     this.loadCoreRules();
 87 |     
 88 |     // Load common rules
 89 |     this.loadCommonRules();
 90 |     
 91 |     // Load essential mode-specific rules
 92 |     this.loadEssentialModeRules(modeName);
 93 |     
 94 |     // Load complexity level rules
 95 |     this.loadComplexityRules(complexityLevel);
 96 |     
 97 |     // Register lazy loaders for specialized functionality
 98 |     this.registerLazyLoaders(modeName, complexityLevel);
 99 |     
100 |     return {
101 |       modeName,
102 |       complexityLevel,
103 |       status: "initialized"
104 |     };
105 |   }
106 |   
107 |   // Load only when specialized functionality is needed
108 |   loadSpecializedRule(ruleType) {
109 |     if (this.lazyLoaders[ruleType]) {
110 |       if (!this.cache.specialized[ruleType]) {
111 |         const rule = this.lazyLoaders[ruleType]();
112 |         this.cache.specialized[ruleType] = rule;
113 |       }
114 |       return this.cache.specialized[ruleType];
115 |     }
116 |     return null;
117 |   }
118 |   
119 |   // Register specialized rule loaders based on mode and complexity
120 |   registerLazyLoaders(modeName, complexityLevel) {
121 |     // Clear existing lazy loaders
122 |     this.lazyLoaders = {};
123 |     
124 |     // Register mode-specific lazy loaders
125 |     if (modeName === "CREATIVE") {
126 |       this.lazyLoaders["architecture"] = () => this.loadRule("creative-phase-architecture.mdc");
127 |       this.lazyLoaders["algorithm"] = () => this.loadRule("creative-phase-algorithm.mdc");
128 |       this.lazyLoaders["uiux"] = () => this.loadRule("creative-phase-uiux.mdc");
129 |     } else if (modeName === "IMPLEMENT") {
130 |       this.lazyLoaders["testing"] = () => this.loadRule("implementation-testing.mdc");
131 |       this.lazyLoaders["deployment"] = () => this.loadRule("implementation-deployment.mdc");
132 |     }
133 |     
134 |     // Register complexity-specific lazy loaders
135 |     if (complexityLevel >= 3) {
136 |       this.lazyLoaders["comprehensive-planning"] = () => this.loadRule("planning-comprehensive.mdc");
137 |       this.lazyLoaders["advanced-verification"] = () => this.loadRule("verification-advanced.mdc");
138 |     }
139 |   }
140 | }
141 | ```
142 | 
143 | ## 📋 RULE DEPENDENCY MAP
144 | 
145 | ```mermaid
146 | graph TD
147 |     Main["main.mdc"] --> Core1["platform-awareness.mdc"]
148 |     Main --> Core2["file-verification.mdc"]
149 |     Main --> Core3["command-execution.mdc"]
150 |     
151 |     subgraph "VAN Mode"
152 |         VanMap["van-mode-map.mdc"] --> Van1["van-complexity-determination.mdc"]
153 |         VanMap --> Van2["van-file-verification.mdc"]
154 |         VanMap --> Van3["van-platform-detection.mdc"]
155 |     end
156 |     
157 |     subgraph "PLAN Mode"
158 |         PlanMap["plan-mode-map.mdc"] --> Plan1["task-tracking-basic.mdc"]
159 |         PlanMap --> Plan2["planning-comprehensive.mdc"]
160 |     end
161 |     
162 |     subgraph "CREATIVE Mode"
163 |         CreativeMap["creative-mode-map.mdc"] --> Creative1["creative-phase-enforcement.mdc"]
164 |         CreativeMap --> Creative2["creative-phase-metrics.mdc"]
165 |         Creative1 & Creative2 -.-> CreativeSpecialized["Specialized Creative Rules"]
166 |         CreativeSpecialized --> CArch["creative-phase-architecture.mdc"]
167 |         CreativeSpecialized --> CAlgo["creative-phase-algorithm.mdc"]
168 |         CreativeSpecialized --> CUIUX["creative-phase-uiux.mdc"]
169 |     end
170 |     
171 |     subgraph "IMPLEMENT Mode"
172 |         ImplementMap["implement-mode-map.mdc"] --> Impl1["implementation-guide.mdc"]
173 |         ImplementMap --> Impl2["testing-strategy.mdc"]
174 |     end
175 | ```
176 | 
177 | ## 🔍 MODE-SPECIFIC RULE LOADING
178 | 
179 | ### VAN Mode Essential Rules
180 | ```markdown
181 | - main.mdc (Core)
182 | - platform-awareness.mdc (Core)
183 | - file-verification.mdc (Core)
184 | - van-mode-map.mdc (Mode)
185 | ```
186 | 
187 | ### PLAN Mode Essential Rules
188 | ```markdown
189 | - main.mdc (Core)
190 | - plan-mode-map.mdc (Mode)
191 | - task-tracking-[complexity].mdc (Level)
192 | ```
193 | 
194 | ### CREATIVE Mode Essential Rules
195 | ```markdown
196 | - main.mdc (Core)
197 | - creative-mode-map.mdc (Mode)
198 | - creative-phase-enforcement.mdc (Mode)
199 | ```
200 | 
201 | ### CREATIVE Mode Specialized Rules (Lazy Loaded)
202 | ```markdown
203 | - creative-phase-architecture.mdc (Specialized)
204 | - creative-phase-algorithm.mdc (Specialized)
205 | - creative-phase-uiux.mdc (Specialized)
206 | ```
207 | 
208 | ### IMPLEMENT Mode Essential Rules
209 | ```markdown
210 | - main.mdc (Core)
211 | - command-execution.mdc (Core)
212 | - implement-mode-map.mdc (Mode)
213 | ```
214 | 
215 | ## 🚀 IMPLEMENTATION BENEFITS
216 | 
217 | The hierarchical loading system provides:
218 | 
219 | 1. **Reduced Initial Loading**: Only essential rules loaded at start (~70% token reduction)
220 | 2. **Cached Core Rules**: Rules shared between modes are cached
221 | 3. **Specialized Rule Loading**: Specialized rules loaded only when needed
222 | 4. **Complexity-Based Loading**: Only load rules appropriate for task complexity
223 | 
224 | ## 📈 TOKEN USAGE COMPARISON
225 | 
226 | | Approach | Initial Tokens | Specialized Tokens | Total Tokens |
227 | |----------|---------------|-------------------|--------------|
228 | | Original System | ~70,000 | Included in initial | ~70,000 |
229 | | Hierarchical System | ~15,000 | ~10,000 (on demand) | ~25,000 |
230 | | **Token Reduction** | **~55,000 (78%)** | **N/A** | **~45,000 (64%)** |
231 | 
232 | ## 🔄 USAGE EXAMPLE
233 | 
234 | ### Example: Creative Phase with Architecture Rule
235 | 
236 | ```javascript
237 | // Initialize the CREATIVE mode with only essential rules
238 | const mode = ruleManager.initializeMode("CREATIVE", 3);
239 | 
240 | // Core and essential mode rules are loaded 
241 | // Architecture rules are NOT loaded yet
242 | 
243 | // Later, when architecture design is needed:
244 | const architectureRule = ruleManager.loadSpecializedRule("architecture");
245 | 
246 | // Now the architecture rule is loaded and cached
247 | ```
248 | 
249 | ## 🧪 RULE LOADING VERIFICATION
250 | 
251 | To ensure the rule loading system is working optimally:
252 | 
253 | ```markdown
254 | ## Rule Loading Verification
255 | 
256 | - Core Rules: [Loaded]
257 | - Mode-Essential Rules: [Loaded]
258 | - Complexity-Level Rules: [Loaded]
259 | - Specialized Rules: [Not Loaded]
260 | 
261 | Current Token Usage: [X] tokens
262 | Potential Token Savings: [Y] tokens
263 | ```
264 | 
265 | This hierarchical approach ensures optimal token usage while maintaining all functionality.


--------------------------------------------------------------------------------
/isolation_rules/Core/memory-bank-paths.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Defines canonical paths for core Memory Bank files.
 3 | globs: documentation\memory-bank-paths.mdc
 4 | alwaysApply: true
 5 | ---
 6 | 
 7 | # CORE MEMORY BANK FILE LOCATIONS
 8 | 
 9 | **CRITICAL:** All core Memory Bank files reside within the `documentation\memory-bank/` directory at the project root. Do NOT create or modify these files outside this directory unless explicitly instructed for archiving purposes.
10 | 
11 | * **Tasks File:** `documentation\memory-bank/tasks.md` - This file is used for active, in-progress task tracking, detailing steps, checklists, and component lists. Its content, particularly the detailed checklists, is merged into the main archive document for the task upon completion. After archival, `tasks.md` is cleared to be ready for the next task. It is an ephemeral working document during a task's lifecycle, with its persistent record captured in the task's archive file.
12 | * **Active Context File:** `documentation\memory-bank/activeContext.md`
13 | * **Progress File:** `documentation\memory-bank/progress.md`
14 | * **Project Brief File:** `documentation\memory-bank/projectbrief.md`
15 | * **Product Context File:** `documentation\memory-bank/productContext.md`
16 | * **System Patterns File:** `documentation\memory-bank/systemPatterns.md`
17 | * **Tech Context File:** `documentation\memory-bank/techContext.md`
18 | * **Style Guide File:** `documentation\memory-bank/style-guide.md`
19 | * **Creative Phase Docs:** `documentation\memory-bank/creative/creative-[feature_name].md`
20 | * **Reflection Docs:** `documentation\memory-bank/reflection/reflection-[task_id].md`
21 | * **Archive Directory:** `documentation\memory-bank/archive/archive-[task_id].md`
22 | 
23 | **Verification Mandate:** Before any `create_file` or `edit_file` operation on these core files, verify the path starts with `documentation\memory-bank/`. If attempting to create a new core file (e.g., `tasks.md` at the start of a project), ensure it is created at `documentation\memory-bank/tasks.md`.
24 | 


--------------------------------------------------------------------------------
/isolation_rules/Core/optimization-integration.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Integration hub for Memory Bank optimizations
  3 | globs: "**/optimization*/**", "**/integration*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # MEMORY BANK OPTIMIZATION INTEGRATION
  8 | 
  9 | > **TL;DR:** This file serves as the integration point for all Memory Bank optimizations, coordinating the various optimization components to work seamlessly together.
 10 | 
 11 | ## 🔄 OPTIMIZATION INTEGRATION FLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["Memory Bank<br>Initialization"] --> HRL["Hierarchical<br>Rule Loading"]
 16 |     HRL --> ACM["Adaptive<br>Complexity Model"]
 17 |     ACM --> DCM["Dynamic<br>Context Management"]
 18 |     DCM --> TMO["Transition<br>Optimization"]
 19 |     
 20 |     subgraph "Level-Specific Optimizations"
 21 |         L1["Level 1<br>Optimizations"]
 22 |         L2["Level 2<br>Optimizations"]
 23 |         L3["Level 3<br>Optimizations"]
 24 |         L4["Level 4<br>Optimizations"]
 25 |     end
 26 |     
 27 |     ACM --> L1 & L2 & L3 & L4
 28 |     
 29 |     L1 & L2 & L3 & L4 --> CPO["Creative Phase<br>Optimization"]
 30 |     
 31 |     CPO --> PDO["Progressive<br>Documentation"]
 32 |     TMO --> PDO
 33 |     
 34 |     PDO --> MBO["Memory Bank<br>Optimization"]
 35 | ```
 36 | 
 37 | ## 📋 OPTIMIZATION COMPONENT REGISTRY
 38 | 
 39 | ```javascript
 40 | // Optimization component registry pseudocode
 41 | const optimizationRegistry = {
 42 |   // Core optimizations
 43 |   hierarchicalRuleLoading: {
 44 |     file: "Core/hierarchical-rule-loading.mdc",
 45 |     dependencies: [],
 46 |     priority: 1
 47 |   },
 48 |   adaptiveComplexityModel: {
 49 |     file: "main-optimized.mdc",
 50 |     dependencies: ["hierarchicalRuleLoading"],
 51 |     priority: 2
 52 |   },
 53 |   modeTransitionOptimization: {
 54 |     file: "Core/mode-transition-optimization.mdc",
 55 |     dependencies: ["hierarchicalRuleLoading", "adaptiveComplexityModel"],
 56 |     priority: 3
 57 |   },
 58 |   
 59 |   // Level-specific optimizations
 60 |   level1Optimization: {
 61 |     file: "Level1/optimized-workflow-level1.mdc",
 62 |     dependencies: ["adaptiveComplexityModel"],
 63 |     priority: 4
 64 |   },
 65 |   
 66 |   // Feature-specific optimizations
 67 |   creativePhaseOptimization: {
 68 |     file: "Phases/CreativePhase/optimized-creative-template.mdc",
 69 |     dependencies: ["hierarchicalRuleLoading", "adaptiveComplexityModel"],
 70 |     priority: 5
 71 |   }
 72 | };
 73 | ```
 74 | 
 75 | ## 🔄 OPTIMIZATION INITIALIZATION SEQUENCE
 76 | 
 77 | ```mermaid
 78 | sequenceDiagram
 79 |     participant MB as Memory Bank
 80 |     participant Reg as Optimization Registry
 81 |     participant HRL as Hierarchical Rule Loading
 82 |     participant ACM as Adaptive Complexity
 83 |     participant TMO as Transition Optimization
 84 |     participant CPO as Creative Phase Optimization
 85 |     
 86 |     MB->>Reg: Request optimization initialization
 87 |     Reg->>Reg: Sort optimizations by priority & dependencies
 88 |     Reg->>HRL: Initialize (Priority 1)
 89 |     HRL-->>Reg: Initialization complete
 90 |     Reg->>ACM: Initialize (Priority 2)
 91 |     ACM->>HRL: Request rule loading services
 92 |     HRL-->>ACM: Provide rule loading
 93 |     ACM-->>Reg: Initialization complete
 94 |     Reg->>TMO: Initialize (Priority 3)
 95 |     TMO->>HRL: Request rule loading services
 96 |     TMO->>ACM: Request complexity model
 97 |     HRL-->>TMO: Provide rule loading
 98 |     ACM-->>TMO: Provide complexity model
 99 |     TMO-->>Reg: Initialization complete
100 |     Reg->>CPO: Initialize (Final)
101 |     CPO->>HRL: Request rule loading services
102 |     CPO->>ACM: Request complexity model
103 |     CPO->>TMO: Request transition services
104 |     HRL-->>CPO: Provide rule loading
105 |     ACM-->>CPO: Provide complexity model
106 |     TMO-->>CPO: Provide transition services
107 |     CPO-->>Reg: Initialization complete
108 |     Reg-->>MB: All optimizations initialized
109 | ```
110 | 
111 | ## 🔍 OPTIMIZATION CONFIGURATION
112 | 
113 | ```javascript
114 | // Optimization configuration pseudocode
115 | const optimizationConfig = {
116 |   // Token optimization settings
117 |   tokenOptimization: {
118 |     enableHierarchicalLoading: true,
119 |     enableProgressiveDocumentation: true,
120 |     enableLazyRuleLoading: true,
121 |     enableContextPruning: true
122 |   },
123 |   
124 |   // Context preservation settings
125 |   contextPreservation: {
126 |     preserveDesignDecisions: true,
127 |     preserveImplementationContext: true,
128 |     preserveUserPreferences: true,
129 |     contextCompressionLevel: "high" // none, low, medium, high
130 |   },
131 |   
132 |   // Documentation optimization
133 |   documentationOptimization: {
134 |     level1DocumentationLevel: "minimal", // minimal, standard, comprehensive
135 |     level2DocumentationLevel: "standard",
136 |     level3DocumentationLevel: "comprehensive",
137 |     level4DocumentationLevel: "comprehensive",
138 |     enableProgressiveDisclosure: true,
139 |     enableTemplateCaching: true
140 |   }
141 | };
142 | ```
143 | 
144 | ## 📊 OPTIMIZATION MONITORING
145 | 
146 | ```mermaid
147 | graph TD
148 |     Monitor["Optimization<br>Monitor"] --> TokenUsage["Token Usage<br>Tracking"]
149 |     Monitor --> ContextEfficiency["Context<br>Efficiency"]
150 |     Monitor --> RuleLoadingStats["Rule Loading<br>Statistics"]
151 |     Monitor --> DocumentationSize["Documentation<br>Size"]
152 |     
153 |     TokenUsage --> Dashboard["Optimization<br>Dashboard"]
154 |     ContextEfficiency --> Dashboard
155 |     RuleLoadingStats --> Dashboard
156 |     DocumentationSize --> Dashboard
157 |     
158 |     Dashboard --> Feedback["Optimization<br>Feedback Loop"]
159 |     Feedback --> Config["Optimization<br>Configuration"]
160 |     Config --> Monitor
161 | ```
162 | 
163 | ## 📈 OPTIMIZATION METRICS
164 | 
165 | ```markdown
166 | # Optimization Metrics
167 | 
168 | ## Token Usage
169 | - Core Rule Loading: [X] tokens
170 | - Mode-Specific Rules: [Y] tokens
171 | - Creative Phase Documentation: [Z] tokens
172 | - Overall Token Reduction: [P]%
173 | 
174 | ## Context Efficiency
175 | - Context Utilization: [Q]%
176 | - Context Waste: [R]%
177 | - Effective Token Capacity: [S] tokens
178 | 
179 | ## Rule Loading
180 | - Rules Loaded: [T] / [U] (Total)
181 | - Lazy-Loaded Rules: [V]
182 | - Cached Rules: [W]
183 | 
184 | ## Documentation
185 | - Level 1 Documentation Size: [X] tokens
186 | - Level 2 Documentation Size: [Y] tokens
187 | - Level 3 Documentation Size: [Z] tokens
188 | - Level 4 Documentation Size: [AA] tokens
189 | ```
190 | 
191 | ## 🔄 INTEGRATION USAGE EXAMPLES
192 | 
193 | ### Initializing All Optimizations
194 | 
195 | ```javascript
196 | // Pseudocode for initializing all optimizations
197 | function initializeMemoryBankOptimizations() {
198 |   // Load optimization registry
199 |   const registry = loadOptimizationRegistry();
200 |   
201 |   // Sort by priority and dependencies
202 |   const sortedOptimizations = sortOptimizations(registry);
203 |   
204 |   // Initialize each optimization in order
205 |   for (const opt of sortedOptimizations) {
206 |     initializeOptimization(opt);
207 |   }
208 |   
209 |   // Configure optimization parameters
210 |   configureOptimizations(loadOptimizationConfig());
211 |   
212 |   // Start monitoring
213 |   initializeOptimizationMonitoring();
214 |   
215 |   return "Memory Bank optimizations initialized";
216 | }
217 | ```
218 | 
219 | ### Using Optimized Creative Phase
220 | 
221 | ```markdown
222 | // Using the optimized creative phase with progressive documentation
223 | 
224 | // Initialize with minimal documentation
225 | 📌 CREATIVE PHASE START: Authentication System
226 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
227 | 
228 | 1️⃣ PROBLEM
229 |    Description: Design an authentication system for the application
230 |    Requirements: Secure, scalable, supports SSO, easy to maintain
231 |    Constraints: Must work with existing user database, <100ms response time
232 | 
233 | 2️⃣ OPTIONS
234 |    Option A: JWT-based stateless auth
235 |    Option B: Session-based auth with Redis
236 |    Option C: OAuth2 implementation
237 | 
238 | // Progressively add detail as needed
239 | 3️⃣ ANALYSIS
240 |    | Criterion | JWT | Sessions | OAuth2 |
241 |    |-----------|-----|----------|--------|
242 |    | Security | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
243 |    | Scalability | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
244 |    | Complexity | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
245 |    
246 | // Focus on decision and implementation
247 | 4️⃣ DECISION
248 |    Selected: Option A: JWT-based auth with refresh tokens
249 |    Rationale: Best balance of performance and scalability
250 |    
251 | 5️⃣ IMPLEMENTATION NOTES
252 |    - Use HS256 algorithm for token signing
253 |    - Implement short-lived access tokens (15min)
254 |    - Store token blacklist in Redis for revocation
255 | ```
256 | 
257 | ## 🔄 MODE TRANSITION EXAMPLE
258 | 
259 | ```markdown
260 | // Optimized mode transition from CREATIVE to IMPLEMENT
261 | 
262 | # MODE TRANSITION: CREATIVE → IMPLEMENT
263 | 
264 | ## Context Summary
265 | - Task: Authentication system implementation
266 | - Complexity: Level 3
267 | - Decision: JWT-based auth with refresh tokens
268 | 
269 | ## Key Context
270 | - Security requirements verified
271 | - Algorithm selection: HS256
272 | - Token lifecycle: 15min access / 7 days refresh
273 | 
274 | ## Next Steps
275 | 1. Implement JWT generation module
276 | 2. Create token validation middleware
277 | 3. Build refresh token handling
278 | 
279 | // Transition happens with preserved context
280 | // IMPLEMENT mode continues with this context available
281 | ```
282 | 
283 | ## 🔄 HIERARCHICAL RULE LOADING EXAMPLE
284 | 
285 | ```javascript
286 | // Pseudocode example of hierarchical rule loading
287 | 
288 | // Initial load - only core rules
289 | loadCoreRules();
290 | 
291 | // Determine complexity
292 | const complexity = determineComplexity();
293 | 
294 | // Load mode-specific essential rules
295 | loadModeEssentialRules("CREATIVE");
296 | 
297 | // Register lazy loaders for specialized rules
298 | registerLazyLoader("architecture", () => loadRule("creative-phase-architecture.mdc"));
299 | registerLazyLoader("algorithm", () => loadRule("creative-phase-algorithm.mdc"));
300 | registerLazyLoader("uiux", () => loadRule("creative-phase-uiux.mdc"));
301 | 
302 | // Later, when architecture design is needed:
303 | const architectureRule = loadSpecializedRule("architecture");
304 | // Architecture rule is now loaded only when needed
305 | ```
306 | 
307 | These integrated optimizations work seamlessly together to provide a significantly more efficient Memory Bank system while maintaining all functionality.


--------------------------------------------------------------------------------
/isolation_rules/Core/platform-awareness.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Platform detection and command adaptation for isolation-focused Memory Bank
 3 | globs: platform-awareness.mdc
 4 | alwaysApply: false
 5 | ---
 6 | 
 7 | 
 8 | # PLATFORM AWARENESS SYSTEM
 9 | 
10 | > **TL;DR:** This system detects the operating system, path format, and shell environment, then adapts commands accordingly to ensure cross-platform compatibility.
11 | 
12 | ## 🔍 PLATFORM DETECTION PROCESS
13 | 
14 | ```mermaid
15 | graph TD
16 |     Start["Start Platform<br>Detection"] --> DetectOS["Detect OS<br>Environment"]
17 |     DetectOS --> Windows["Windows<br>Detection"]
18 |     DetectOS --> Mac["macOS<br>Detection"]
19 |     DetectOS --> Linux["Linux<br>Detection"]
20 |     
21 |     Windows & Mac & Linux --> PathCheck["Path Separator<br>Detection"]
22 |     PathCheck --> CmdAdapt["Command<br>Adaptation"]
23 |     CmdAdapt --> ShellCheck["Shell Type<br>Detection"]
24 |     ShellCheck --> Complete["Platform Detection<br>Complete"]
25 | ```
26 | 
27 | ## 📋 PLATFORM DETECTION IMPLEMENTATION
28 | 
29 | For reliable platform detection:
30 | 
31 | ```
32 | ## Platform Detection Results
33 | Operating System: [Windows/macOS/Linux]
34 | Path Separator: [\ or /]
35 | Shell Environment: [PowerShell/Bash/Zsh/Cmd]
36 | Command Adaptation: [Required/Not Required]
37 | 
38 | Adapting commands for [detected platform]...
39 | ```
40 | 
41 | ## 🔍 PATH FORMAT CONVERSION
42 | 
43 | When converting paths between formats:
44 | 
45 | ```mermaid
46 | sequenceDiagram
47 |     participant Input as Path Input
48 |     participant Detector as Format Detector
49 |     participant Converter as Format Converter
50 |     participant Output as Adapted Path
51 |     
52 |     Input->>Detector: Raw Path
53 |     Detector->>Detector: Detect Current Format
54 |     Detector->>Converter: Path + Current Format
55 |     Converter->>Converter: Apply Target Format
56 |     Converter->>Output: Platform-Specific Path
57 | ```
58 | 
59 | ## 📝 PLATFORM VERIFICATION CHECKLIST
60 | 
61 | ```
62 | ✓ PLATFORM VERIFICATION
63 | - Operating system correctly identified? [YES/NO]
64 | - Path separator format detected? [YES/NO]
65 | - Shell environment identified? [YES/NO]
66 | - Command set adapted appropriately? [YES/NO]
67 | - Path format handling configured? [YES/NO]
68 | 
69 | → If all YES: Platform adaptation complete
70 | → If any NO: Run additional detection steps
71 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Level1/optimized-workflow-level1.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Optimized Level 1 workflow for quick bug fixes with token efficiency
  3 | globs: "**/level1*/**", "**/quick*/**", "**/bugfix*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # OPTIMIZED LEVEL 1 WORKFLOW
  8 | 
  9 | > **TL;DR:** This streamlined workflow for Level 1 tasks (quick bug fixes) optimizes for speed and token efficiency while maintaining quality.
 10 | 
 11 | ## 🔧 LEVEL 1 PROCESS FLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["START LEVEL 1<br>QUICK FIX"] --> Analyze["1️⃣ ANALYZE<br>Understand issue"]
 16 |     Analyze --> Implement["2️⃣ IMPLEMENT<br>Fix the issue"]
 17 |     Implement --> Verify["3️⃣ VERIFY<br>Test the fix"]
 18 |     Verify --> Document["4️⃣ DOCUMENT<br>Record solution"]
 19 | 
 20 | ```
 21 | 
 22 | ## 📝 CONSOLIDATED DOCUMENTATION
 23 | 
 24 | Level 1 tasks use a single-file approach to minimize context switching:
 25 | 
 26 | ```markdown
 27 | # QUICK FIX: [Issue Name]
 28 | 
 29 | ## Issue Summary
 30 | - Type: [Bug/Hotfix/Quick Enhancement]
 31 | - Priority: [Low/Medium/High/Critical]
 32 | - Reported by: [Name/System]
 33 | - Affected area: [Component/Feature]
 34 | 
 35 | ## Analysis
 36 | - Root cause: [Brief description]
 37 | - Affected files: [List of files]
 38 | - Impact: [Scope of impact]
 39 | 
 40 | ## Solution
 41 | - Approach: [Brief description]
 42 | - Changes made: [List of changes]
 43 | - Commands executed: [Key commands]
 44 | 
 45 | ## Verification
 46 | - Testing: [How the fix was tested]
 47 | - Results: [Test results]
 48 | - Additional checks: [Any other verification]
 49 | 
 50 | ## Status
 51 | - [x] Fix implemented
 52 | - [x] Tests passed
 53 | - [x] Documentation updated
 54 | ```
 55 | 
 56 | ## 🔄 MEMORY BANK UPDATE
 57 | 
 58 | Level 1 tasks use a simplified Memory Bank update with minimal overhead:
 59 | 
 60 | ```markdown
 61 | ## tasks.md Update (Level 1)
 62 | 
 63 | ### Task: [Task Name]
 64 | - Status: Complete
 65 | - Implementation: [One-line summary]
 66 | - Link to fix: [File/line reference]
 67 | ```
 68 | 
 69 | ## ⚡ TOKEN-OPTIMIZED TEMPLATE
 70 | 
 71 | For maximum efficiency, Level 1 tasks can use this ultra-compact template:
 72 | 
 73 | ```markdown
 74 | ## 🔧 FIX: [Issue]
 75 | 📌 Problem: [Brief description]
 76 | 🔍 Cause: [Root cause]
 77 | 🛠️ Solution: [Implemented fix]
 78 | ✅ Tested: [Verification method]
 79 | ```
 80 | 
 81 | ## 🔄 AUTO-DOCUMENTATION HELPERS
 82 | 
 83 | Use these helpers to automatically generate documentation:
 84 | 
 85 | ```javascript
 86 | function generateLevel1Documentation(issue, rootCause, solution, verification) {
 87 |   return `## 🔧 FIX: ${issue}
 88 | 📌 Problem: ${issue}
 89 | 🔍 Cause: ${rootCause}
 90 | 🛠️ Solution: ${solution}
 91 | ✅ Tested: ${verification}`;
 92 | }
 93 | ```
 94 | 
 95 | ## 📊 QUICK TEMPLATES FOR COMMON ISSUES
 96 | 
 97 | ### Performance Fix
 98 | ```markdown
 99 | ## 🔧 FIX: Performance issue in [component]
100 | 📌 Problem: Slow response times in [component]
101 | 🔍 Cause: Inefficient query/algorithm
102 | 🛠️ Solution: Optimized [specific optimization]
103 | ✅ Tested: Response time improved from [X]ms to [Y]ms
104 | ```
105 | 
106 | ### Bug Fix
107 | ```markdown
108 | ## 🔧 FIX: Bug in [component]
109 | 📌 Problem: [Specific behavior] not working correctly
110 | 🔍 Cause: [Root cause analysis]
111 | 🛠️ Solution: Fixed by [implementation details]
112 | ✅ Tested: Verified with [test approach]
113 | ```
114 | 
115 | ### Quick Enhancement
116 | ```markdown
117 | ## 🔧 ENHANCEMENT: [Feature]
118 | 📌 Request: Add [specific capability]
119 | 🛠️ Implementation: Added by [implementation details]
120 | ✅ Tested: Verified with [test approach]
121 | ```
122 | 
123 | ## ✅ STREAMLINED VERIFICATION
124 | 
125 | Level 1 tasks use a minimal verification process:
126 | 
127 | ```markdown
128 | VERIFICATION:
129 | [x] Fix implemented and tested
130 | [x] No regressions introduced
131 | [x] Documentation updated
132 | ```
133 | 
134 | ## 🚀 CONSOLIDATED MEMORY BANK UPDATE
135 | 
136 | Optimize Memory Bank updates for Level 1 tasks by using a single operation:
137 | 
138 | ```javascript
139 | // Pseudocode for optimized Level 1 Memory Bank update
140 | function updateLevel1MemoryBank(taskInfo) {
141 |   // Read current tasks.md
142 |   const tasksContent = readFile("tasks.md");
143 |   
144 |   // Create minimal update
145 |   const updateBlock = `
146 | ### Task: ${taskInfo.name}
147 | - Status: Complete
148 | - Implementation: ${taskInfo.solution}
149 | - Link to fix: ${taskInfo.fileReference}
150 | `;
151 |   
152 |   // Add update to tasks.md
153 |   const updatedContent = appendToSection(tasksContent, "Completed Tasks", updateBlock);
154 |   
155 |   // Write in single operation
156 |   writeFile("tasks.md", updatedContent);
157 |   
158 |   return "Memory Bank updated";
159 | }
160 | ```
161 | 
162 | ## 🔄 OPTIMIZED LEVEL 1 WORKFLOW EXAMPLE
163 | 
164 | ```markdown
165 | ## 🔧 FIX: Login button not working on mobile devices
166 | 
167 | 📌 Problem: 
168 | Users unable to log in on mobile devices, button appears but doesn't trigger authentication
169 | 
170 | 🔍 Cause:
171 | Event listener using desktop-specific event (mousedown instead of handling touch events)
172 | 
173 | 🛠️ Solution:
174 | Updated event handling to use event delegation and support both mouse and touch events:
175 | ```js
176 | // Before: 
177 | loginButton.addEventListener('mousedown', handleLogin);
178 | 
179 | // After:
180 | loginButton.addEventListener('mousedown', handleLogin);
181 | loginButton.addEventListener('touchstart', handleLogin);
182 | ```
183 | 
184 | ✅ Tested:
185 | - Verified on iOS Safari and Android Chrome 
186 | - Login now works on all tested mobile devices
187 | - No regression on desktop browsers
188 | ```
189 | 
190 | ## ⚡ TOKEN EFFICIENCY BENEFITS
191 | 
192 | This optimized Level 1 workflow provides:
193 | 
194 | 1. Reduced documentation overhead (70% reduction)
195 | 2. Consolidated Memory Bank updates (single operation vs. multiple)
196 | 3. Focused verification process (essential checks only)
197 | 4. Template-based approach for common scenarios
198 | 5. Streamlined workflow with fewer steps
199 | 
200 | The updated approach maintains all critical information while significantly reducing token usage.


--------------------------------------------------------------------------------
/isolation_rules/Level1/quick-documentation.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Quick documentation approach for Level 1 Quick Bug Fix tasks
  3 | globs: "**/level1/**", "**/documentation/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # QUICK DOCUMENTATION FOR LEVEL 1 TASKS
  8 | 
  9 | > **TL;DR:** This document outlines a quick documentation approach for Level 1 (Quick Bug Fix) tasks, ensuring that essential information is captured with minimal overhead.
 10 | 
 11 | ## 🔍 QUICK DOCUMENTATION OVERVIEW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     FixComplete["Bug Fix<br>Complete"] --> Document["Document<br>Solution"]
 16 |     Document --> UpdateTasks["Update<br>tasks.md"]
 17 |     UpdateTasks --> MinimalUpdates["Make Minimal<br>Memory Bank Updates"]
 18 |     MinimalUpdates --> CrossReference["Create Simple<br>Cross-References"]
 19 |     CrossReference --> Complete["Documentation<br>Complete"]
 20 | ```
 21 | 
 22 | Level 1 tasks require efficient documentation that captures essential information without unnecessary detail. This approach ensures that critical knowledge is preserved while maintaining speed and efficiency.
 23 | 
 24 | ## 📋 DOCUMENTATION PRINCIPLES
 25 | 
 26 | 1. **Conciseness**: Keep documentation brief but complete
 27 | 2. **Focus**: Document only what's necessary to understand the fix
 28 | 3. **Context**: Provide sufficient context to understand the issue
 29 | 4. **Solution**: Clearly describe what was changed and why
 30 | 5. **Findability**: Ensure the fix can be easily found later
 31 | 
 32 | ## 📋 QUICK FIX DOCUMENTATION TEMPLATE
 33 | 
 34 | ```markdown
 35 | # Quick Fix: [Issue Title]
 36 | 
 37 | ## Issue
 38 | [Brief description of the problem - 1-2 sentences]
 39 | 
 40 | ## Root Cause
 41 | [Concise description of what caused the issue - 1-2 sentences]
 42 | 
 43 | ## Solution
 44 | [Brief description of the fix implemented - 2-3 sentences]
 45 | 
 46 | ## Files Changed
 47 | - [File path 1]
 48 | - [File path 2]
 49 | 
 50 | ## Verification
 51 | [How the fix was tested/verified - 1-2 sentences]
 52 | 
 53 | ## Notes
 54 | [Any additional information that might be helpful - optional]
 55 | ```
 56 | 
 57 | ## 📋 TASKS.MD UPDATES
 58 | 
 59 | For Level 1 tasks, update tasks.md with this format:
 60 | 
 61 | ```markdown
 62 | ## Completed Bug Fixes
 63 | - [X] [Level 1] Fixed: [Issue title] (Completed: YYYY-MM-DD)
 64 |   - Issue: [One-line description]
 65 |   - Root Cause: [One-line description]
 66 |   - Solution: [One-line description]
 67 |   - Files: [File paths]
 68 | ```
 69 | 
 70 | For in-progress tasks:
 71 | 
 72 | ```markdown
 73 | ## Bug Fixes in Progress
 74 | - [ ] [Level 1] Fix: [Issue title] (Est: XX mins)
 75 |   - Issue: [One-line description]
 76 |   - Location: [Component/file]
 77 | ```
 78 | 
 79 | ## 📋 MEMORY BANK UPDATES
 80 | 
 81 | For Level 1 tasks, make these minimal Memory Bank updates:
 82 | 
 83 | 1. **tasks.md**:
 84 |    - Update with fix details as shown above
 85 |    - Mark task as complete
 86 | 
 87 | 2. **activeContext.md** (only if relevant):
 88 |    ```markdown
 89 |    ## Recent Fixes
 90 |    - [YYYY-MM-DD] Fixed [issue] in [component/file]. [One-line description of fix]
 91 |    ```
 92 | 
 93 | 3. **progress.md** (only if significant):
 94 |    ```markdown
 95 |    ## Bug Fixes
 96 |    - [YYYY-MM-DD] Fixed [issue] in [component/file].
 97 |    ```
 98 | 
 99 | Other Memory Bank files typically do not need updates for Level 1 tasks unless the fix reveals important system information.
100 | 
101 | ## 📋 COMMON BUG CATEGORIES
102 | 
103 | Categorize bugs to improve documentation consistency:
104 | 
105 | 1. **Logic Error**:
106 |    - Example: "Fixed incorrect conditional logic in user validation"
107 | 
108 | 2. **UI/Display Issue**:
109 |    - Example: "Fixed misaligned button in mobile view"
110 | 
111 | 3. **Performance Issue**:
112 |    - Example: "Fixed slow loading of user profile data"
113 | 
114 | 4. **Data Handling Error**:
115 |    - Example: "Fixed incorrect parsing of date format"
116 | 
117 | 5. **Configuration Issue**:
118 |    - Example: "Fixed incorrect environment variable setting"
119 | 
120 | ## 📋 QUICK DOCUMENTATION PROCESS
121 | 
122 | Follow these steps for efficient documentation:
123 | 
124 | 1. **Immediately After Fix**:
125 |    - Document while the fix is fresh in your mind
126 |    - Focus on what, why, and how
127 |    - Be specific about changes made
128 | 
129 | 2. **Update Task Tracking**:
130 |    - Update tasks.md with fix details
131 |    - Use consistent format for easy reference
132 | 
133 | 3. **Minimal Cross-References**:
134 |    - Create only essential cross-references
135 |    - Ensure fix can be found in the future
136 | 
137 | 4. **Check Completeness**:
138 |    - Verify all essential information is captured
139 |    - Ensure another developer could understand the fix
140 | 
141 | ## 📋 EXAMPLES: GOOD VS. INSUFFICIENT DOCUMENTATION
142 | 
143 | ### ❌ Insufficient Documentation
144 | 
145 | ```markdown
146 | Fixed the login bug.
147 | ```
148 | 
149 | ### ✅ Good Documentation
150 | 
151 | ```markdown
152 | # Quick Fix: User Login Failure with Special Characters
153 | 
154 | ## Issue
155 | Users with special characters in email addresses (e.g., +, %) couldn't log in.
156 | 
157 | ## Root Cause
158 | The email validation regex was incorrectly escaping special characters.
159 | 
160 | ## Solution
161 | Updated the email validation regex in AuthValidator.js to properly handle special characters according to RFC 5322.
162 | 
163 | ## Files Changed
164 | - src/utils/AuthValidator.js
165 | 
166 | ## Verification
167 | Tested login with various special characters in email addresses (test+user@example.com, user%123@example.com).
168 | ```
169 | 
170 | ## 📋 DOCUMENTATION VERIFICATION CHECKLIST
171 | 
172 | ```
173 | ✓ DOCUMENTATION VERIFICATION
174 | - Issue clearly described? [YES/NO]
175 | - Root cause identified? [YES/NO]
176 | - Solution explained? [YES/NO]
177 | - Files changed listed? [YES/NO]
178 | - Verification method described? [YES/NO]
179 | - tasks.md updated? [YES/NO]
180 | - Memory Bank minimally updated? [YES/NO]
181 | 
182 | → If all YES: Documentation complete
183 | → If any NO: Complete missing information
184 | ```
185 | 
186 | ## 📋 MINIMAL MODE DOCUMENTATION
187 | 
188 | For minimal mode, use this ultra-compact format:
189 | 
190 | ```
191 | ✓ FIX: [Issue title]
192 | ✓ CAUSE: [One-line root cause]
193 | ✓ SOLUTION: [One-line fix description]
194 | ✓ FILES: [File paths]
195 | ✓ VERIFIED: [How verified]
196 | ```
197 | 
198 | ## 🔄 DOCUMENTATION INTEGRATION
199 | 
200 | Quick documentation integrates with other systems:
201 | 
202 | ```mermaid
203 | graph TD
204 |     QuickDoc["Quick Fix<br>Documentation"] --> TasksMD["tasks.md<br>Update"]
205 |     QuickDoc --> FixDetails["Fix Details<br>Documentation"]
206 |     
207 |     TasksMD --> Tracking["Task<br>Tracking"]
208 |     FixDetails --> Knowledge["Knowledge<br>Preservation"]
209 |     
210 |     Tracking & Knowledge --> Future["Future<br>Reference"]
211 | ```
212 | 
213 | ## 🚨 DOCUMENTATION EFFICIENCY PRINCIPLE
214 | 
215 | Remember:
216 | 
217 | ```
218 | ┌─────────────────────────────────────────────────────┐
219 | │ Document ONLY what's needed to understand the fix.  │
220 | │ Focus on ESSENTIAL information that would help      │
221 | │ someone who encounters the same issue in the future.│
222 | └─────────────────────────────────────────────────────┘
223 | ```
224 | 
225 | This ensures that Level 1 tasks are documented efficiently without unnecessary overhead while preserving critical knowledge.
226 | 


--------------------------------------------------------------------------------
/isolation_rules/Level1/workflow-level1.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Streamlined workflow for Level 1 Quick Bug Fix tasks
  3 | globs: "**/level1/**", "**/workflow/**"
  4 | alwaysApply: false
  5 | ---
  6 | # STREAMLINED WORKFLOW FOR LEVEL 1 TASKS
  7 | 
  8 | > **TL;DR:** This document outlines a streamlined workflow for Level 1 (Quick Bug Fix) tasks, focusing on efficient problem resolution with minimal overhead while maintaining adequate documentation.
  9 | 
 10 | ## 🔍 LEVEL 1 WORKFLOW OVERVIEW
 11 | 
 12 | ```mermaid
 13 | graph LR
 14 |     Init["1. INITIALIZATION"] --> Impl["2. IMPLEMENTATION"]
 15 |     Impl --> Doc["3. DOCUMENTATION"]
 16 |     
 17 |     %% Document connections for each phase
 18 |     Init -.-> InitDocs["Quick setup<br>Issue understanding"]
 19 |     Impl -.-> ImplDocs["Focused fix<br>Verify resolution"]
 20 |     Doc -.-> DocDocs["Document solution<br>Update tracking"]
 21 | ```
 22 | 
 23 | ## 📋 WORKFLOW PHASES
 24 | 
 25 | ### Phase 1: INITIALIZATION
 26 | 
 27 | ```mermaid
 28 | graph TD
 29 |     Start["Start Level 1 Task"] --> Identify["Identify<br>Issue"]
 30 |     Identify --> Understand["Understand<br>Problem"]
 31 |     Understand --> Setup["Quick<br>Environment Setup"]
 32 |     Setup --> TaskEntry["Create Quick<br>Task Entry"]
 33 |     TaskEntry --> InitComplete["Initialization<br>Complete"]
 34 | ```
 35 | 
 36 | **Steps:**
 37 | 1. Identify the specific issue to fix
 38 | 2. Understand the problem and its impact
 39 | 3. Set up environment for quick fix
 40 | 4. Create minimal task entry in tasks.md
 41 | 
 42 | **Milestone Checkpoint:**
 43 | ```
 44 | ✓ INITIALIZATION CHECKPOINT
 45 | - Issue clearly identified? [YES/NO]
 46 | - Problem understood? [YES/NO]
 47 | - Environment set up? [YES/NO]
 48 | - Task entry created? [YES/NO]
 49 | 
 50 | → If all YES: Proceed to Implementation
 51 | → If any NO: Complete initialization steps
 52 | ```
 53 | 
 54 | ### Phase 2: IMPLEMENTATION
 55 | 
 56 | ```mermaid
 57 | graph TD
 58 |     Start["Begin<br>Implementation"] --> Locate["Locate<br>Issue Source"]
 59 |     Locate --> Develop["Develop<br>Fix"]
 60 |     Develop --> Test["Test<br>Solution"]
 61 |     Test --> Verify["Verify<br>Resolution"]
 62 |     Verify --> ImplComplete["Implementation<br>Complete"]
 63 | ```
 64 | 
 65 | **Steps:**
 66 | 1. Locate the source of the issue
 67 | 2. Develop a targeted fix
 68 | 3. Test the solution thoroughly
 69 | 4. Verify that the issue is resolved
 70 | 
 71 | **Milestone Checkpoint:**
 72 | ```
 73 | ✓ IMPLEMENTATION CHECKPOINT
 74 | - Issue source located? [YES/NO]
 75 | - Fix developed? [YES/NO]
 76 | - Solution tested? [YES/NO]
 77 | - Resolution verified? [YES/NO]
 78 | 
 79 | → If all YES: Proceed to Documentation
 80 | → If any NO: Complete implementation steps
 81 | ```
 82 | 
 83 | ### Phase 3: DOCUMENTATION
 84 | 
 85 | ```mermaid
 86 | graph TD
 87 |     Start["Begin<br>Documentation"] --> Update["Update<br>tasks.md"]
 88 |     Update --> Solution["Document<br>Solution"]
 89 |     Solution --> References["Create Minimal<br>Cross-References"]
 90 |     References --> NotifyStakeholders["Notify<br>Stakeholders"]
 91 |     NotifyStakeholders --> DocComplete["Documentation<br>Complete"]
 92 | ```
 93 | 
 94 | **Steps:**
 95 | 1. Update tasks.md with fix details
 96 | 2. Document the solution concisely
 97 | 3. Create minimal cross-references
 98 | 4. Notify stakeholders as needed
 99 | 
100 | **Milestone Checkpoint:**
101 | ```
102 | ✓ DOCUMENTATION CHECKPOINT
103 | - tasks.md updated? [YES/NO]
104 | - Solution documented? [YES/NO]
105 | - Cross-references created? [YES/NO]
106 | - Stakeholders notified? [YES/NO]
107 | 
108 | → If all YES: Task Complete
109 | → If any NO: Complete documentation steps
110 | ```
111 | 
112 | ## 📋 TASK STRUCTURE IN TASKS.MD
113 | 
114 | For Level 1 tasks, use this minimal structure:
115 | 
116 | ```markdown
117 | ## Bug Fixes in Progress
118 | - [ ] [Level 1] Fix: [Bug description] (Est: XX mins)
119 | 
120 | ## Completed Bug Fixes
121 | - [X] [Level 1] Fixed: [Bug description] (Completed: YYYY-MM-DD)
122 |   - Issue: [Brief issue description]
123 |   - Solution: [Brief solution description]
124 |   - Files changed: [File paths]
125 | ```
126 | 
127 | ## 📋 MEMORY BANK UPDATES
128 | 
129 | For Level 1 tasks, make minimal Memory Bank updates:
130 | 
131 | 1. **tasks.md**: Update with fix details
132 | 2. **activeContext.md**: Brief mention of fix if relevant
133 | 3. **progress.md**: Add to list of completed fixes
134 | 
135 | ## 📋 WORKFLOW VERIFICATION CHECKLIST
136 | 
137 | ```
138 | ✓ FINAL WORKFLOW VERIFICATION
139 | - Issue identified and understood? [YES/NO]
140 | - Fix implemented and verified? [YES/NO]
141 | - tasks.md updated? [YES/NO]
142 | - Solution documented? [YES/NO]
143 | - Memory Bank minimally updated? [YES/NO]
144 | 
145 | → If all YES: Level 1 Task Successfully Completed
146 | → If any NO: Address outstanding items
147 | ```
148 | 
149 | ## 📋 TASK ESCALATION
150 | 
151 | If during the Level 1 process you discover the task is more complex:
152 | 
153 | ```
154 | ⚠️ TASK ESCALATION NEEDED
155 | Current Level: Level 1
156 | Recommended Level: Level [2/3/4]
157 | Reason: [Brief explanation]
158 | 
159 | Would you like me to escalate this task to Level [2/3/4]?
160 | ```
161 | 
162 | Escalation indicators:
163 | 1. Fix requires changes to multiple components
164 | 2. Solution requires design decisions
165 | 3. Testing reveals broader issues
166 | 4. Fix impacts core functionality
167 | 
168 | ## 🔄 INTEGRATION WITH MEMORY BANK
169 | 
170 | ```mermaid
171 | graph TD
172 |     Workflow["Level 1<br>Workflow"] --> TM["Update<br>tasks.md"]
173 |     Workflow --> AC["Minimal Update<br>activeContext.md"]
174 |     Workflow --> PM["Brief Update<br>progress.md"]
175 |     
176 |     TM & AC & PM --> MB["Memory Bank<br>Integration"]
177 |     MB --> NextTask["Transition to<br>Next Task"]
178 | ```
179 | 
180 | ## 🚨 EFFICIENCY PRINCIPLE
181 | 
182 | Remember:
183 | 
184 | ```
185 | ┌─────────────────────────────────────────────────────┐
186 | │ Level 1 workflow prioritizes SPEED and EFFICIENCY.  │
187 | │ Minimize process overhead while ensuring adequate   │
188 | │ documentation of the solution.                     │
189 | └─────────────────────────────────────────────────────┘
190 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Level2/archive-basic.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Basic archiving approach for Level 2 Simple Enhancement tasks
  3 | globs: "**/level2/**", "**/archive/**", "**/completion/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # BASIC ARCHIVING FOR LEVEL 2 TASKS
  8 | 
  9 | > **TL;DR:** This document outlines a basic archiving approach for Level 2 (Simple Enhancement) tasks, ensuring that completed work is properly documented and knowledge is preserved with minimal overhead.
 10 | 
 11 | ## 🔍 ARCHIVING OVERVIEW
 12 | 
 13 | Even for Level 2 tasks, proper archiving ensures that completed work is documented and knowledge is preserved. This basic archiving approach provides sufficient structure while maintaining efficiency.
 14 | 
 15 | ## 📋 ARCHIVING PRINCIPLES
 16 | 
 17 | 1. **Completion**: Clearly document what was completed
 18 | 2. **Context**: Preserve the context of the enhancement
 19 | 3. **Knowledge**: Capture key insights and lessons
 20 | 4. **Findability**: Make archived information easy to find
 21 | 5. **References**: Create cross-references to related work
 22 | 
 23 | ## 📋 BASIC ARCHIVE STRUCTURE
 24 | 
 25 | ```markdown
 26 | # Enhancement Archive: [Feature Name]
 27 | 
 28 | ## Summary
 29 | [Brief summary of the enhancement]
 30 | 
 31 | ## Date Completed
 32 | YYYY-MM-DD
 33 | 
 34 | ## Key Files Modified
 35 | - [File path 1]
 36 | - [File path 2]
 37 | - [File path 3]
 38 | 
 39 | ## Requirements Addressed
 40 | - [Requirement 1]
 41 | - [Requirement 2]
 42 | - [Requirement 3]
 43 | 
 44 | ## Implementation Details
 45 | [Brief description of how the enhancement was implemented]
 46 | 
 47 | ## Testing Performed
 48 | - [Test 1]
 49 | - [Test 2]
 50 | - [Test 3]
 51 | 
 52 | ## Lessons Learned
 53 | - [Lesson 1]
 54 | - [Lesson 2]
 55 | - [Lesson 3]
 56 | 
 57 | ## Related Work
 58 | - [Link to related task/enhancement 1]
 59 | - [Link to related task/enhancement 2]
 60 | 
 61 | ## Notes
 62 | [Any additional information or context]
 63 | ```
 64 | 
 65 | ## 📋 ARCHIVE LOCATION
 66 | 
 67 | Store archives in an organized structure:
 68 | 
 69 | ```
 70 | docs/
 71 | └── archive/
 72 |     └── enhancements/
 73 |         └── YYYY-MM/
 74 |             ├── feature-name-1.md
 75 |             └── feature-name-2.md
 76 | ```
 77 | 
 78 | ## 📋 ARCHIVING PROCESS
 79 | 
 80 | Follow these steps to archive a Level 2 task:
 81 | 
 82 | 1. **Prepare Archive Content**:
 83 |    - Gather all relevant information
 84 |    - Fill in the archive template
 85 |    - Include all key implementation details
 86 | 
 87 | 2. **Cross-Reference Creation**:
 88 |    - Update tasks.md with link to archive
 89 |    - Add reference in progress.md
 90 |    - Update activeContext.md with next focus
 91 | 
 92 | 3. **File Creation and Storage**:
 93 |    - Create appropriate directory if needed
 94 |    - Save archive file with descriptive name
 95 |    - Ensure file follows naming convention
 96 | 
 97 | 4. **Final Verification**:
 98 |    - Check archive for completeness
 99 |    - Verify all cross-references
100 |    - Ensure all links are working
101 | 
102 | ## 📋 CROSS-REFERENCE FORMAT
103 | 
104 | When creating cross-references:
105 | 
106 | 1. **In tasks.md**:
107 |    ```markdown
108 |    ## Completed Enhancements
109 |    - [X] [Feature Name] (YYYY-MM-DD) - [Archive Link](../docs/archive/enhancements/YYYY-MM/feature-name.md)
110 |    ```
111 | 
112 | 2. **In progress.md**:
113 |    ```markdown
114 |    ## Completed Milestones
115 |    - [Feature Name] enhancement completed on YYYY-MM-DD. See [archive entry](../docs/archive/enhancements/YYYY-MM/feature-name.md).
116 |    ```
117 | 
118 | 3. **In activeContext.md**:
119 |    ```markdown
120 |    ## Recently Completed
121 |    - [Feature Name] enhancement is now complete. Archive: [link](../docs/archive/enhancements/YYYY-MM/feature-name.md)
122 |    
123 |    ## Current Focus
124 |    - Moving to [Next Task Name]
125 |    ```
126 | 
127 | ## 📋 ARCHIVING VERIFICATION CHECKLIST
128 | 
129 | ```
130 | ✓ ARCHIVE VERIFICATION
131 | - Archive content complete? [YES/NO]
132 | - Archive properly stored? [YES/NO]
133 | - Cross-references created? [YES/NO]
134 | - tasks.md updated? [YES/NO]
135 | - progress.md updated? [YES/NO]
136 | - activeContext.md updated? [YES/NO]
137 | 
138 | → If all YES: Archiving complete
139 | → If any NO: Complete archiving process
140 | ```
141 | 
142 | ## 📋 MINIMAL MODE ARCHIVING
143 | 
144 | For minimal mode, use this format:
145 | 
146 | ```
147 | ✓ ARCHIVE: [Feature Name]
148 | ✓ DATE: YYYY-MM-DD
149 | ✓ FILES: [Key files changed]
150 | ✓ SUMMARY: [One-sentence summary]
151 | ✓ LESSONS: [Key takeaway]
152 | ✓ REFS: [tasks.md, progress.md, activeContext.md]
153 | ```
154 | 
155 | ## 🔄 INTEGRATION WITH MEMORY BANK
156 | 
157 | Archiving integrates with Memory Bank:
158 | 
159 | ```mermaid
160 | graph TD
161 |     Archive["Enhancement<br>Archive"] --> TasksUpdate["Update<br>tasks.md"]
162 |     Archive --> ProgressUpdate["Update<br>progress.md"]
163 |     Archive --> ContextUpdate["Update<br>activeContext.md"]
164 |     
165 |     TasksUpdate & ProgressUpdate & ContextUpdate --> CrossLinks["Create<br>Cross-Links"]
166 |     CrossLinks --> Verify["Verify<br>References"]
167 | ```
168 | 
169 | ## 🚨 KNOWLEDGE PRESERVATION PRINCIPLE
170 | 
171 | Remember:
172 | 
173 | ```
174 | ┌─────────────────────────────────────────────────────┐
175 | │ Archive files are a VALUABLE KNOWLEDGE RESOURCE.    │
176 | │ Take care to preserve insights and lessons that     │
177 | │ will benefit future work.                           │
178 | └─────────────────────────────────────────────────────┘
179 | ```
180 | 
181 | This ensures that knowledge is preserved and can be referenced in the future. 


--------------------------------------------------------------------------------
/isolation_rules/Level2/reflection-basic.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Basic reflection format for Level 2 Simple Enhancement tasks
  3 | globs: "**/level2/**", "**/reflection/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # BASIC REFLECTION FOR LEVEL 2 TASKS
  8 | 
  9 | > **TL;DR:** This document outlines a basic reflection approach for Level 2 (Simple Enhancement) tasks, ensuring that key insights and lessons are captured without unnecessary overhead.
 10 | 
 11 | ## 🔍 REFLECTION OVERVIEW
 12 | 
 13 | Reflection is essential for improving future work, even for simpler Level 2 enhancements. This basic reflection approach focuses on key outcomes, challenges, and lessons learned while maintaining efficiency.
 14 | 
 15 | ## 📋 REFLECTION PRINCIPLES
 16 | 
 17 | 1. **Honesty**: Accurately represent successes and challenges
 18 | 2. **Specificity**: Include concrete examples and observations
 19 | 3. **Insight**: Go beyond surface observations to derive useful insights
 20 | 4. **Improvement**: Focus on actionable takeaways for future work
 21 | 5. **Efficiency**: Keep reflection concise and focused on key learnings
 22 | 
 23 | ## 📋 BASIC REFLECTION STRUCTURE
 24 | 
 25 | ```markdown
 26 | # Level 2 Enhancement Reflection: [Feature Name]
 27 | 
 28 | ## Enhancement Summary
 29 | [Brief one-paragraph summary of the enhancement]
 30 | 
 31 | ## What Went Well
 32 | - [Specific success point 1]
 33 | - [Specific success point 2]
 34 | - [Specific success point 3]
 35 | 
 36 | ## Challenges Encountered
 37 | - [Specific challenge 1]
 38 | - [Specific challenge 2]
 39 | - [Specific challenge 3]
 40 | 
 41 | ## Solutions Applied
 42 | - [Solution to challenge 1]
 43 | - [Solution to challenge 2]
 44 | - [Solution to challenge 3]
 45 | 
 46 | ## Key Technical Insights
 47 | - [Technical insight 1]
 48 | - [Technical insight 2]
 49 | - [Technical insight 3]
 50 | 
 51 | ## Process Insights
 52 | - [Process insight 1]
 53 | - [Process insight 2]
 54 | - [Process insight 3]
 55 | 
 56 | ## Action Items for Future Work
 57 | - [Specific action item 1]
 58 | - [Specific action item 2]
 59 | - [Specific action item 3]
 60 | 
 61 | ## Time Estimation Accuracy
 62 | - Estimated time: [X hours/days]
 63 | - Actual time: [Y hours/days]
 64 | - Variance: [Z%]
 65 | - Reason for variance: [Brief explanation]
 66 | ```
 67 | 
 68 | ## 📋 REFLECTION QUALITY
 69 | 
 70 | High-quality reflections for Level 2 tasks should:
 71 | 
 72 | 1. **Provide specific examples** rather than vague statements
 73 | 2. **Identify concrete takeaways** not general observations
 74 | 3. **Connect challenges to solutions** with clear reasoning
 75 | 4. **Analyze estimation accuracy** to improve future planning
 76 | 5. **Generate actionable improvements** for future work
 77 | 
 78 | ## 📋 REFLECTION PROCESS
 79 | 
 80 | Follow these steps for effective Level 2 task reflection:
 81 | 
 82 | 1. **Schedule Reflection**:
 83 |    - Allocate dedicated time for reflection
 84 |    - Complete reflection within 24 hours of task completion
 85 | 
 86 | 2. **Gather Information**:
 87 |    - Review the original task requirements
 88 |    - Examine implementation details
 89 |    - Consider challenges encountered
 90 |    - Review time tracking data
 91 | 
 92 | 3. **Complete Template**:
 93 |    - Fill in all sections of the reflection template
 94 |    - Include specific, concrete examples
 95 |    - Be honest about challenges
 96 | 
 97 | 4. **Extract Insights**:
 98 |    - Identify patterns in challenges
 99 |    - Connect challenges to potential future improvements
100 |    - Consider process improvements
101 | 
102 | 5. **Document Action Items**:
103 |    - Create specific, actionable improvements
104 |    - Link these to future tasks where applicable
105 | 
106 | 6. **Store Reflection**:
107 |    - Save reflection with the task archive
108 |    - Add cross-references to relevant documents
109 | 
110 | ## 📋 EXAMPLES: VAGUE VS. SPECIFIC ENTRIES
111 | 
112 | ### ❌ Vague Entries (Insufficient)
113 | 
114 | - "The implementation went well."
115 | - "We had some challenges with the code."
116 | - "The feature works as expected."
117 | 
118 | ### ✅ Specific Entries (Sufficient)
119 | 
120 | - "The modular approach allowed for easy integration with the existing codebase, specifically the clean separation between the UI layer and data processing logic."
121 | - "Challenge: The state management became complex when handling multiple user interactions. Solution: Implemented a more structured reducer pattern with clear actions and state transitions."
122 | - "Action Item: Create a reusable component for file selection that handles all the edge cases we encountered in this implementation."
123 | 
124 | ## 📋 REFLECTION VERIFICATION CHECKLIST
125 | 
126 | ```
127 | ✓ REFLECTION VERIFICATION
128 | - All template sections completed? [YES/NO]
129 | - Specific examples provided? [YES/NO]
130 | - Challenges honestly addressed? [YES/NO]
131 | - Concrete solutions documented? [YES/NO]
132 | - Actionable insights generated? [YES/NO]
133 | - Time estimation analyzed? [YES/NO]
134 | 
135 | → If all YES: Reflection complete
136 | → If any NO: Improve reflection quality
137 | ```
138 | 
139 | ## 📋 MINIMAL MODE REFLECTION
140 | 
141 | For minimal mode, use this format:
142 | 
143 | ```
144 | ✓ REFLECTION: [Feature Name]
145 | ✓ WENT WELL: [Key success]
146 | ✓ CHALLENGE: [Key challenge]
147 | ✓ SOLUTION: [Key solution]
148 | ✓ INSIGHT: [Most important takeaway]
149 | ✓ ACTION: [Top priority action item]
150 | ✓ TIME: Est [X] vs. Actual [Y] ([Z%] variance)
151 | ```
152 | 
153 | ## 🔄 INTEGRATION WITH MEMORY BANK
154 | 
155 | Reflection integrates with Memory Bank:
156 | 
157 | ```mermaid
158 | graph TD
159 |     Reflection["Enhancement<br>Reflection"] --> Archive["Add to<br>Archive"]
160 |     Reflection --> ProgressUpdate["Update<br>progress.md"]
161 |     Reflection --> ActionItems["Document<br>Action Items"]
162 |     
163 |     ActionItems --> Tasks["Add to<br>tasks.md"]
164 |     Archive & ProgressUpdate & Tasks --> CrossLinks["Create<br>Cross-Links"]
165 | ```
166 | 
167 | ## 🚨 CONTINUOUS IMPROVEMENT PRINCIPLE
168 | 
169 | Remember:
170 | 
171 | ```
172 | ┌─────────────────────────────────────────────────────┐
173 | │ Every reflection should produce at least ONE        │
174 | │ actionable improvement for future work.             │
175 | └─────────────────────────────────────────────────────┘
176 | ```
177 | 
178 | This ensures that reflection directly contributes to ongoing improvement of both the product and the process. 


--------------------------------------------------------------------------------
/isolation_rules/Level2/task-tracking-basic.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Basic task tracking for Level 2 Simple Enhancement tasks
  3 | globs: "**/level2/**", "**/tracking/**", "**/task/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # BASIC TASK TRACKING FOR LEVEL 2
  8 | 
  9 | > **TL;DR:** This document outlines a streamlined task tracking approach for Level 2 (Simple Enhancement) tasks. It provides a balanced framework for managing task progress with minimal overhead.
 10 | 
 11 | ## 🔍 TASK TRACKING OVERVIEW
 12 | 
 13 | Level 2 tasks require a more structured tracking approach than Level 1, but don't need the comprehensive tracking of higher-level tasks. This basic tracking system provides sufficient structure while maintaining efficiency.
 14 | 
 15 | ## 📋 TASK TRACKING PRINCIPLES
 16 | 
 17 | 1. **Clarity**: Tasks should be clearly defined
 18 | 2. **Visibility**: Progress should be visible at a glance
 19 | 3. **Structure**: Break work into logical subtasks
 20 | 4. **Updates**: Keep progress regularly updated
 21 | 5. **Completion**: Clearly mark when tasks are done
 22 | 
 23 | ## 📋 TASK STRUCTURE FOR LEVEL 2
 24 | 
 25 | ```markdown
 26 | ## [Feature Name] Enhancement
 27 | 
 28 | **Status**: [Not Started/In Progress/Complete]
 29 | **Priority**: [High/Medium/Low]
 30 | **Estimated Effort**: [Small/Medium/Large]
 31 | 
 32 | ### Description
 33 | [Brief description of the enhancement]
 34 | 
 35 | ### Requirements
 36 | - [Requirement 1]
 37 | - [Requirement 2]
 38 | - [Requirement 3]
 39 | 
 40 | ### Subtasks
 41 | - [ ] [Subtask 1]
 42 | - [ ] [Subtask 2]
 43 | - [ ] [Subtask 3]
 44 | 
 45 | ### Dependencies
 46 | - [Dependency 1]
 47 | - [Dependency 2]
 48 | 
 49 | ### Notes
 50 | [Any additional information or context]
 51 | ```
 52 | 
 53 | ## 📋 TASKS.MD ORGANIZATION
 54 | 
 55 | Organize tasks.md with these sections for Level 2 tasks:
 56 | 
 57 | ```markdown
 58 | # Tasks
 59 | 
 60 | ## Active Enhancements
 61 | - [Enhancement 1] - [Status]
 62 | - [Enhancement 2] - [Status]
 63 | 
 64 | ## Enhancement Details
 65 | ### [Enhancement 1]
 66 | [Task structure as above]
 67 | 
 68 | ### [Enhancement 2]
 69 | [Task structure as above]
 70 | 
 71 | ## Completed Enhancements
 72 | - [X] [Completed Enhancement 1] (YYYY-MM-DD)
 73 | - [X] [Completed Enhancement 2] (YYYY-MM-DD)
 74 | ```
 75 | 
 76 | ## 📋 UPDATING TASK STATUS
 77 | 
 78 | Update tasks using this process:
 79 | 
 80 | 1. **Starting a Task**:
 81 |    - Update Status to "In Progress"
 82 |    - Add start date to Notes
 83 | 
 84 | 2. **Progress Updates**:
 85 |    - Check off subtasks as completed
 86 |    - Add brief notes about progress
 87 |    - Update any changed requirements
 88 | 
 89 | 3. **Completing a Task**:
 90 |    - Update Status to "Complete"
 91 |    - Check off all subtasks
 92 |    - Move to Completed Enhancements
 93 |    - Add completion date
 94 | 
 95 | ## 📋 SUBTASK MANAGEMENT
 96 | 
 97 | For Level 2 tasks, subtasks should:
 98 | 
 99 | 1. Be actionable and specific
100 | 2. Represent approximately 30-60 minutes of work
101 | 3. Follow a logical sequence
102 | 4. Be updated as soon as completed
103 | 5. Include verification steps
104 | 
105 | Example of well-structured subtasks:
106 | ```markdown
107 | ### Subtasks
108 | - [ ] Review existing implementation of related features
109 | - [ ] Create draft UI design for new button
110 | - [ ] Add HTML structure for new component
111 | - [ ] Implement button functionality in JavaScript
112 | - [ ] Add appropriate styling in CSS
113 | - [ ] Add event handling
114 | - [ ] Test on desktop browsers
115 | - [ ] Test on mobile browsers
116 | - [ ] Update user documentation
117 | ```
118 | 
119 | ## 📋 PROGRESS VISUALIZATION
120 | 
121 | Use progress indicators to show status:
122 | 
123 | ```markdown
124 | ### Progress
125 | [###-------] 30% Complete
126 | ```
127 | 
128 | For subtasks:
129 | ```markdown
130 | ### Subtasks (3/10 Complete)
131 | - [X] Subtask 1
132 | - [X] Subtask 2
133 | - [X] Subtask 3
134 | - [ ] Subtask 4
135 | - [ ] Subtask 5
136 | ```
137 | 
138 | ## 📋 TRACKING VERIFICATION CHECKLIST
139 | 
140 | ```
141 | ✓ TASK TRACKING VERIFICATION
142 | - Task clearly defined? [YES/NO]
143 | - Requirements listed? [YES/NO]
144 | - Subtasks created? [YES/NO]
145 | - Dependencies identified? [YES/NO]
146 | - Status up-to-date? [YES/NO]
147 | 
148 | → If all YES: Task tracking is adequate
149 | → If any NO: Update task tracking
150 | ```
151 | 
152 | ## 📋 MINIMAL MODE TRACKING
153 | 
154 | For minimal mode, use this format:
155 | 
156 | ```
157 | ✓ TASK: [Enhancement name]
158 | ✓ STATUS: [In Progress/Complete]
159 | ✓ SUBTASKS: [X/Y Complete]
160 | ✓ NEXT: [Next action]
161 | ```
162 | 
163 | ## 🔄 INTEGRATION WITH MEMORY BANK
164 | 
165 | Task tracking integrates with Memory Bank:
166 | 
167 | ```mermaid
168 | graph TD
169 |     TasksFile["tasks.md"] --> Active["activeContext.md"]
170 |     TasksFile --> Progress["progress.md"]
171 |     
172 |     Active -->|"Current focus"| TasksFile
173 |     Progress -->|"Completion status"| TasksFile
174 | ```
175 | 
176 | ## 🚨 TASKS.MD PRIMACY PRINCIPLE
177 | 
178 | Remember:
179 | 
180 | ```
181 | ┌─────────────────────────────────────────────────────┐
182 | │ tasks.md is the SINGLE SOURCE OF TRUTH for ALL      │
183 | │ task tracking. ALL task updates MUST be reflected   │
184 | │ in tasks.md IMMEDIATELY.                            │
185 | └─────────────────────────────────────────────────────┘
186 | ```
187 | 
188 | This ensures everyone has visibility into current task status at all times. 


--------------------------------------------------------------------------------
/isolation_rules/Level2/workflow-level2.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Basic workflow for Level 2 Simple Enhancement tasks
  3 | globs: "**/level2/**", "**/workflow/**"
  4 | alwaysApply: false
  5 | ---
  6 | # WORKFLOW FOR LEVEL 2 TASKS
  7 | 
  8 | > **TL;DR:** This document outlines a structured yet efficient workflow for Level 2 (Simple Enhancement) tasks, including 6 key phases with milestone checkpoints and quality verification.
  9 | 
 10 | ## 🔍 LEVEL 2 WORKFLOW OVERVIEW
 11 | 
 12 | ```mermaid
 13 | graph LR
 14 |     Init["1. INITIALIZATION"] --> Doc["2. DOCUMENTATION<br>SETUP"]
 15 |     Doc --> Plan["3. TASK<br>PLANNING"]
 16 |     Plan --> Impl["4. IMPLEMENTATION"]
 17 |     Impl --> Reflect["5. REFLECTION"]
 18 |     Reflect --> Archive["6. ARCHIVING"]
 19 |     
 20 |     %% Document connections for each phase
 21 |     Init -.-> InitDocs["INITIALIZATION"]
 22 |     Doc -.-> DocDocs["DOCUMENTATION"]
 23 |     Plan -.-> PlanDocs["PLANNING"]
 24 |     Impl -.-> ImplDocs["IMPLEMENTATION"]
 25 |     Reflect -.-> ReflectDocs["REFLECTION"]
 26 |     Archive -.-> ArchiveDocs["ARCHIVING"]
 27 | ```
 28 | 
 29 | Level 2 tasks involve simple enhancements that require a structured approach with moderate planning and documentation. This workflow provides the right balance of process and efficiency.
 30 | 
 31 | ## 📋 WORKFLOW PHASES
 32 | 
 33 | ### Phase 1: INITIALIZATION
 34 | 
 35 | ```mermaid
 36 | graph TD
 37 |     Start["Start Level 2 Task"] --> Platform{"Detect<br>Platform"}
 38 |     Platform --> FileCheck["Critical File<br>Verification"]
 39 |     FileCheck --> LoadStructure["Load Memory<br>Bank Structure"]
 40 |     LoadStructure --> TaskCreation["Create Task<br>in tasks.md"]
 41 |     TaskCreation --> SetupComplete["Initialization<br>Complete"]
 42 | ```
 43 | 
 44 | **Steps:**
 45 | 1. Platform detection
 46 | 2. Critical file verification
 47 | 3. Memory Bank structure loading
 48 | 4. Task creation in tasks.md
 49 | 5. Initial task scope definition
 50 | 
 51 | **Milestone Checkpoint:**
 52 | ```
 53 | ✓ INITIALIZATION CHECKPOINT
 54 | - Platform detected and configured? [YES/NO]
 55 | - Critical files verified? [YES/NO]
 56 | - Memory Bank loaded? [YES/NO]
 57 | - Task created in tasks.md? [YES/NO]
 58 | - Initial scope defined? [YES/NO]
 59 | 
 60 | → If all YES: Proceed to Documentation Setup
 61 | → If any NO: Complete initialization steps
 62 | ```
 63 | 
 64 | ### Phase 2: DOCUMENTATION SETUP
 65 | 
 66 | ```mermaid
 67 | graph TD
 68 |     Start["Begin Documentation<br>Setup"] --> LoadTemplate["Load Basic<br>Documentation Templates"]
 69 |     LoadTemplate --> UpdateProject["Update<br>projectbrief.md"]
 70 |     UpdateProject --> UpdateContext["Update<br>activeContext.md"]
 71 |     UpdateContext --> SetupComplete["Documentation<br>Setup Complete"]
 72 | ```
 73 | 
 74 | **Steps:**
 75 | 1. Load basic documentation templates
 76 | 2. Update projectbrief.md with enhancement details
 77 | 3. Update activeContext.md with current focus
 78 | 4. Create minimal documentation structure
 79 | 
 80 | **Milestone Checkpoint:**
 81 | ```
 82 | ✓ DOCUMENTATION CHECKPOINT
 83 | - Documentation templates loaded? [YES/NO]
 84 | - projectbrief.md updated? [YES/NO]
 85 | - activeContext.md updated? [YES/NO]
 86 | - Documentation structure created? [YES/NO]
 87 | 
 88 | → If all YES: Proceed to Task Planning
 89 | → If any NO: Complete documentation setup
 90 | ```
 91 | 
 92 | ### Phase 3: TASK PLANNING
 93 | 
 94 | ```mermaid
 95 | graph TD
 96 |     Start["Begin Task<br>Planning"] --> Requirements["Define Clear<br>Requirements"]
 97 |     Requirements --> SubTasks["Break Down<br>Into Subtasks"]
 98 |     SubTasks --> TasksUpdate["Update tasks.md<br>With Subtasks"]
 99 |     TasksUpdate --> TimeEstimate["Create Time<br>Estimates"]
100 |     TimeEstimate --> PlanComplete["Planning<br>Complete"]
101 | ```
102 | 
103 | **Steps:**
104 | 1. Define clear requirements
105 | 2. Break down into subtasks
106 | 3. Update tasks.md with subtasks
107 | 4. Create time estimates
108 | 5. Document dependencies and constraints
109 | 
110 | **Milestone Checkpoint:**
111 | ```
112 | ✓ PLANNING CHECKPOINT
113 | - Requirements clearly defined? [YES/NO]
114 | - Task broken down into subtasks? [YES/NO]
115 | - tasks.md updated with subtasks? [YES/NO]
116 | - Time estimates created? [YES/NO]
117 | - Dependencies documented? [YES/NO]
118 | 
119 | → If all YES: Proceed to Implementation
120 | → If any NO: Complete planning steps
121 | ```
122 | 
123 | ### Phase 4: IMPLEMENTATION
124 | 
125 | ```mermaid
126 | graph TD
127 |     Start["Begin<br>Implementation"] --> SubTask1["Complete<br>Subtask 1"]
128 |     SubTask1 --> UpdateStatus1["Update Status<br>in tasks.md"]
129 |     UpdateStatus1 --> SubTask2["Complete<br>Subtask 2"]
130 |     SubTask2 --> UpdateStatus2["Update Status<br>in tasks.md"]
131 |     UpdateStatus2 --> FinalSubTask["Complete<br>Final Subtask"]
132 |     FinalSubTask --> Verification["Perform<br>Verification"]
133 |     Verification --> ImplComplete["Implementation<br>Complete"]
134 | ```
135 | 
136 | **Steps:**
137 | 1. Implement first subtask
138 | 2. Update status in tasks.md
139 | 3. Implement remaining subtasks
140 | 4. Regular status updates after each subtask
141 | 5. Verify complete implementation
142 | 
143 | **Milestone Checkpoint:**
144 | ```
145 | ✓ IMPLEMENTATION CHECKPOINT
146 | - All subtasks completed? [YES/NO]
147 | - Status updates maintained? [YES/NO]
148 | - Enhancement fully implemented? [YES/NO]
149 | - Basic verification performed? [YES/NO]
150 | - tasks.md fully updated? [YES/NO]
151 | 
152 | → If all YES: Proceed to Reflection
153 | → If any NO: Complete implementation steps
154 | ```
155 | 
156 | ### Phase 5: REFLECTION
157 | 
158 | ```mermaid
159 | graph TD
160 |     Start["Begin<br>Reflection"] --> Template["Load Reflection<br>Template"]
161 |     Template --> Review["Review Completed<br>Enhancement"]
162 |     Review --> Document["Document Successes<br>and Challenges"]
163 |     Document --> Insights["Extract Key<br>Insights"]
164 |     Insights --> Actions["Define Action<br>Items"]
165 |     Actions --> ReflectComplete["Reflection<br>Complete"]
166 | ```
167 | 
168 | **Steps:**
169 | 1. Load reflection template
170 | 2. Review completed enhancement
171 | 3. Document successes and challenges
172 | 4. Extract key insights
173 | 5. Define action items for future work
174 | 
175 | **Milestone Checkpoint:**
176 | ```
177 | ✓ REFLECTION CHECKPOINT
178 | - Reflection template loaded? [YES/NO]
179 | - Enhancement reviewed? [YES/NO]
180 | - Successes and challenges documented? [YES/NO]
181 | - Key insights extracted? [YES/NO]
182 | - Action items defined? [YES/NO]
183 | 
184 | → If all YES: Proceed to Archiving
185 | → If any NO: Complete reflection steps
186 | ```
187 | 
188 | ### Phase 6: ARCHIVING
189 | 
190 | ```mermaid
191 | graph TD
192 |     Start["Begin<br>Archiving"] --> Template["Load Archive<br>Template"]
193 |     Template --> Gather["Gather Implementation<br>Details"]
194 |     Gather --> Create["Create Archive<br>Document"]
195 |     Create --> CrossRef["Create Cross-<br>References"]
196 |     CrossRef --> Update["Update Memory<br>Bank Files"]
197 |     Update --> ArchiveComplete["Archiving<br>Complete"]
198 | ```
199 | 
200 | **Steps:**
201 | 1. Load archive template
202 | 2. Gather implementation details
203 | 3. Create archive document
204 | 4. Create cross-references
205 | 5. Update Memory Bank files
206 | 
207 | **Milestone Checkpoint:**
208 | ```
209 | ✓ ARCHIVING CHECKPOINT
210 | - Archive template loaded? [YES/NO]
211 | - Implementation details gathered? [YES/NO]
212 | - Archive document created? [YES/NO]
213 | - Cross-references created? [YES/NO]
214 | - Memory Bank files updated? [YES/NO]
215 | 
216 | → If all YES: Task Complete
217 | → If any NO: Complete archiving steps
218 | ```
219 | 
220 | ## 📋 WORKFLOW VERIFICATION CHECKLIST
221 | 
222 | ```
223 | ✓ FINAL WORKFLOW VERIFICATION
224 | - All phases completed? [YES/NO]
225 | - All milestone checkpoints passed? [YES/NO]
226 | - tasks.md fully updated? [YES/NO]
227 | - Reflection document created? [YES/NO]
228 | - Archive document created? [YES/NO]
229 | - Memory Bank fully updated? [YES/NO]
230 | 
231 | → If all YES: Level 2 Task Successfully Completed
232 | → If any NO: Address outstanding items
233 | ```
234 | 
235 | ## 📋 MINIMAL MODE WORKFLOW
236 | 
237 | For minimal mode, use this streamlined workflow:
238 | 
239 | ```
240 | 1. INIT: Verify environment, create task entry
241 | 2. DOCS: Update projectbrief and activeContext
242 | 3. PLAN: Define requirements, subtasks, estimates
243 | 4. IMPL: Complete subtasks, update status
244 | 5. REFLECT: Document key insights and actions
245 | 6. ARCHIVE: Document completion and cross-reference
246 | ```
247 | 
248 | ## 🔄 LEVEL TRANSITION HANDLING
249 | 
250 | ```mermaid
251 | graph TD
252 |     L2["Level 2 Task"] --> Assess["Continuous<br>Assessment"]
253 |     
254 |     Assess --> Down["Downgrade to<br>Level 1"]
255 |     Assess --> Up["Upgrade to<br>Level 3/4"]
256 |     
257 |     Down --> L1Trigger["Triggers:<br>- Simpler than expected<br>- Quick fix possible<br>- Single component"]
258 |     
259 |     Up --> L34Trigger["Triggers:<br>- More complex<br>- Multiple components<br>- Design needed"]
260 |     
261 |     L1Trigger --> L1Switch["Switch to<br>Level 1 Workflow"]
262 |     L34Trigger --> L34Switch["Switch to<br>Level 3/4 Workflow"]
263 | ```
264 | 
265 | ## 🔄 INTEGRATION WITH MEMORY BANK
266 | 
267 | ```mermaid
268 | graph TD
269 |     Workflow["Level 2<br>Workflow"] --> PB["Update<br>projectbrief.md"]
270 |     Workflow --> AC["Update<br>activeContext.md"]
271 |     Workflow --> TM["Maintain<br>tasks.md"]
272 |     Workflow --> PM["Update<br>progress.md"]
273 |     
274 |     PB & AC & TM & PM --> MB["Memory Bank<br>Integration"]
275 |     MB --> NextTask["Transition to<br>Next Task"]
276 | ```
277 | 
278 | ## 🚨 EFFICIENCY PRINCIPLE
279 | 
280 | Remember:
281 | 
282 | ```
283 | ┌─────────────────────────────────────────────────────┐
284 | │ Level 2 workflow balances PROCESS with EFFICIENCY.  │
285 | │ Follow the structure but avoid unnecessary overhead. │
286 | └─────────────────────────────────────────────────────┘
287 | ```
288 | 
289 | This ensures that simple enhancements are implemented with the right level of documentation and process. 


--------------------------------------------------------------------------------
/isolation_rules/Level3/archive-intermediate.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: 
 3 | globs: archive-intermediate.mdc
 4 | alwaysApply: false
 5 | ---
 6 | 
 7 | # LEVEL 3 ARCHIVE: INTERMEDIATE FEATURE DOCUMENTATION
 8 | 
 9 | > **TL;DR:** This guide outlines the archiving process for a completed Level 3 intermediate feature. The aim is to create a self-contained, easily accessible record of the feature's development lifecycle, including its planning, design decisions, implementation summary, and reflection.
10 | 
11 | ## 🚀 Before You Start Archiving (L3 Pre-Archive Checklist)
12 | 
13 | 1.  **Confirm Reflection Complete:** Verify in `documentation\memory-bank/tasks.md` that the reflection phase for this feature is marked as complete and `documentation\memory-bank/reflection-[feature_id].md` exists and is finalized.
14 | 2.  **Gather All Feature-Specific Documents:**
15 |     * The feature plan section from `documentation\memory-bank/tasks.md` (or a copy of it).
16 |     * All `documentation\memory-bank/creative/creative-[aspect_name].md` documents related to this feature.
17 |     * The `documentation\memory-bank/reflection/reflection-[feature_id].md` document.
18 |     * Key diagrams or architectural notes from `documentation\memory-bank/progress.md` if not captured elsewhere.
19 |     * A link to the primary commit(s) or feature branch merge for the implemented code.
20 | 
21 | ## 📦 Level 3 Archiving Workflow
22 | 
23 | ```mermaid
24 | graph TD
25 |     StartArchive["Start L3 Archiving"] -->
26 |     VerifyReflect["1. Verify Reflection Complete<br>Check `tasks.md` & `reflection-[feature_id].md`"] -->
27 |     GatherDocs["2. Gather All Feature Documents<br>(Plan, Creative outputs, Reflection, Code links)"] -->
28 |     CreateArchiveFile["3. Create Feature Archive File<br>e.g., `documentation\memory-bank/archive/feature-[FeatureNameOrID]_YYYYMMDD.md`"] -->
29 |     PopulateArchive["4. Populate Archive File<br>(Using L3 Archive Template below)"] -->
30 |     VerifyLinks["5. Verify All Internal Links<br>in Archive File are Correct"] -->
31 |     FinalUpdateTasks["6. Final Update to `tasks.md`<br>(Mark Feature FULLY COMPLETED & ARCHIVED, link to archive file)"] -->
32 |     UpdateProgressFile["7. Add Final Entry to `progress.md`<br>(Note archiving & link to archive file)"] -->
33 |     ClearActiveCtx["8. Clear `activeContext.md`<br>Reset for Next Task/Project"] -->
34 |     ArchiveDone["L3 Archiving Complete<br>Feature successfully documented and closed."]
35 | ````
36 | 
37 | ## 📝 Structure for `documentation\memory-bank/archive/feature-[FeatureNameOrID]_YYYYMMDD.md`
38 | 
39 |   * **Feature Title:** (e.g., "Archive: User Profile Feature - Avatar Upload Enhancement")
40 |   * **Feature ID (from `tasks.md`):**
41 |   * **Date Archived:** YYYY-MM-DD
42 |   * **Status:** COMPLETED & ARCHIVED
43 |   * **1. Feature Overview:**
44 |       * Brief description of the feature and its purpose (can be extracted from `tasks.md` or `projectbrief.md`).
45 |       * Link to the original task entry/plan in `tasks.md` (if `tasks.md` is versioned or kept historically).
46 |   * **2. Key Requirements Met:**
47 |       * List the main functional and non-functional requirements this feature addressed.
48 |   * **3. Design Decisions & Creative Outputs:**
49 |       * Summary of key design choices.
50 |       * Direct links to all relevant `documentation\memory-bank/creative/creative-[aspect_name].md` documents.
51 |       * Link to `documentation\memory-bank/style-guide.md` version used (if applicable).
52 |   * **4. Implementation Summary:**
53 |       * High-level overview of how the feature was implemented.
54 |       * List of primary new components/modules created.
55 |       * Key technologies or libraries utilized specifically for this feature.
56 |       * Link to the main feature branch merge commit or primary code location/pull request.
57 |   * **5. Testing Overview:**
58 |       * Brief summary of the testing strategy employed for this feature (unit, integration, E2E).
59 |       * Outcome of the testing.
60 |   * **6. Reflection & Lessons Learned:**
61 |       * Direct link to `documentation\memory-bank/reflection/reflection-[feature_id].md`.
62 |       * Optionally, copy 1-2 most critical lessons directly into the archive summary.
63 |   * **7. Known Issues or Future Considerations (Optional, if any remaining from reflection):**
64 |       * Any minor known issues deferred.
65 |       * Potential future enhancements related to this feature.
66 | 
67 | ### Key Files and Components Affected (from tasks.md)
68 | [Summary or direct copy of file/component checklists from the original tasks.md for this project. This provides a quick reference to the scope of changes at a component/file level.]
69 | 
70 | ## 📌 What to Emphasize in L3 Archiving
71 | 
72 |   * **Self-Contained Feature Record:** The goal is to have a go-to document in the archive that summarizes the "story" of this feature.
73 |   * **Traceability:** Easy navigation from the archive summary to detailed planning, design, and reflection documents.
74 |   * **Maintainability Focus:** Information that would help a future developer understand, maintain, or build upon this specific feature.
75 |   * **Not a Full System Archive:** Unlike Level 4, this is not about archiving the entire application state, but rather the lifecycle of one significant feature.
76 | 


--------------------------------------------------------------------------------
/isolation_rules/Level3/implementation-intermediate.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: 
 3 | globs: implementation-intermediate.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # LEVEL 3 IMPLEMENTATION: BUILDING INTERMEDIATE FEATURES
 7 | 
 8 | > **TL;DR:** This guide focuses on the systematic implementation of a planned and designed Level 3 feature. It emphasizes modular development, strict adherence to creative decisions and the style guide, integration with existing systems, and thorough feature-specific testing.
 9 | 
10 | ## 🛠️ Level 3 Feature Implementation Workflow
11 | 
12 | This workflow outlines the typical steps for building an intermediate feature.
13 | 
14 | ```mermaid
15 | graph TD
16 |     StartImpl["Start L3 Implementation"] -->
17 |     ReviewDocs["1. Review All Relevant Docs<br>(Tasks, Creative Docs, Style Guide)"] -->
18 |     SetupEnv["2. Setup/Verify Dev Environment<br>(Branch, Tools, Dependencies)"] -->
19 |     ModuleBreakdown["3. Break Down Feature into Modules/Major Components<br>(Based on plan in `tasks.md`)"] -->
20 |     BuildIterate["4. Implement Modules/Components Iteratively"]
21 | 
22 |     BuildIterate --> ImplementModule["4a. Select Next Module/Component"]
23 |     ImplementModule --> CodeModule["4b. Code Module<br>(Adhere to design, style guide, coding standards)"]
24 |     CodeModule --> UnitTests["4c. Write & Pass Unit Tests"]
25 |     UnitTests --> SelfReview["4d. Self-Review/Code Linting"]
26 |     SelfReview --> MoreModules{"4e. More Modules<br>for this Feature?"}
27 |     MoreModules -- Yes --> ImplementModule
28 | 
29 |     MoreModules -- No --> IntegrateModules["5. Integrate All Feature Modules/Components"]
30 |     IntegrateModules --> IntegrationTesting["6. Perform Integration Testing<br>(Feature modules + existing system parts)"]
31 |     IntegrationTesting --> E2EFeatureTesting["7. End-to-End Feature Testing<br>(Validate against user stories & requirements)"]
32 |     E2EFeatureTesting --> AccessibilityCheck["8. Accessibility & Responsiveness Check<br>(If UI is involved)"]
33 |     AccessibilityCheck --> CodeCleanup["9. Code Cleanup & Refinement"]
34 |     CodeCleanup --> UpdateMB["10. Update Memory Bank<br>(`tasks.md` sub-tasks, `progress.md` details)"]
35 |     UpdateMB --> FinalFeatureReview["11. Final Feature Review (Conceptual Peer Review if possible)"]
36 |     FinalFeatureReview --> ImplementationDone["L3 Implementation Complete<br>Ready for REFLECT Mode"]
37 | ````
38 | 
39 | ## 🔑 Key Considerations for Level 3 Implementation
40 | 
41 |   * **Modularity & Encapsulation:** Design and build the feature in well-defined, reusable, and loosely coupled modules or components.
42 |   * **Adherence to Design:** Strictly follow the decisions documented in `documentation\memory-bank/creative-*.md` files and the `documentation\memory-bank/style-guide.md`. Deviations must be justified and documented.
43 |   * **State Management:** If the feature introduces or significantly interacts with complex application state, ensure the state management strategy (potentially defined in CREATIVE mode) is correctly implemented and tested.
44 |   * **API Interactions:**
45 |       * If consuming new or existing APIs, ensure requests and responses are handled correctly, including error states.
46 |       * If exposing new API endpoints as part of the feature, ensure they are robust, secure, and documented.
47 |   * **Error Handling:** Implement user-friendly error messages and robust error handling within the feature's scope.
48 |   * **Performance:** Be mindful of performance implications. Avoid common pitfalls like N+1 database queries, inefficient algorithms, or large asset loading without optimization, especially if identified as a concern in the PLAN or CREATIVE phase.
49 |   * **Security:** Implement with security best practices in mind, particularly for features handling user input, authentication, or sensitive data. Refer to any security design decisions from CREATIVE mode.
50 | 
51 | ## 🧪 Testing Focus for Level 3 Features
52 | 
53 |   * **Unit Tests:** Each new function, method, or logical unit within the feature's components should have corresponding unit tests. Aim for good coverage of core logic and edge cases.
54 |   * **Component Tests (for UI features):** Test UI components in isolation, verifying rendering, props handling, and event emissions.
55 |   * **Integration Tests:** Crucial for L3. Test how the different modules/components of the new feature work together. Also, test how the completed feature integrates with existing parts of the application it interacts with.
56 |   * **User Scenario / Acceptance Tests (Feature-Specific):** Validate that the feature fulfills its defined requirements and user stories from the user's perspective. This can be manual or automated.
57 | 
58 | ## 📝 Documentation During Implementation
59 | 
60 |   * **`documentation\memory-bank/tasks.md`:** Update the status of sub-tasks related to the feature as they are completed. Note any blockers or changes in estimates.
61 |   * **`documentation\memory-bank/progress.md`:** Make regular entries detailing:
62 |       * Modules/components completed.
63 |       * Key decisions made during implementation (if minor and not warranting a full CREATIVE cycle).
64 |       * Files significantly modified
65 |       * Test results for major integration points.
66 |       * Any deviations from the plan or creative designs, with rationale.
67 |   * **Code Comments:** Write clear, concise comments explaining complex logic, assumptions, or TODOs.
68 |   * **READMEs (if applicable):** If the feature introduces new modules or libraries that require specific setup or usage notes, consider adding or updating relevant README files.
69 | 


--------------------------------------------------------------------------------
/isolation_rules/Level3/planning-comprehensive.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: planning comprehensive
  3 | globs: planning-comprehensive.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # LEVEL 3 COMPREHENSIVE PLANNING
  7 | 
  8 | > **TL;DR:** This document provides structured planning guidelines for Level 3 (Intermediate Feature) tasks, focusing on comprehensive planning with creative phases and clear implementation strategies.
  9 | 
 10 | ## 🏗️ PLANNING WORKFLOW
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["Planning Start"] --> Req["📋 Requirements<br>Analysis"]
 15 |     Req --> Comp["🔍 Component<br>Analysis"]
 16 |     Comp --> Design["🎨 Design<br>Decisions"]
 17 |     Design --> Impl["⚙️ Implementation<br>Strategy"]
 18 |     Impl --> Test["🧪 Testing<br>Strategy"]
 19 |     Test --> Doc["📚 Documentation<br>Plan"]
 20 |     
 21 |     Design --> Creative["Creative Phases:"]
 22 |     Creative --> UI["UI/UX Design"]
 23 |     Creative --> Arch["Architecture"]
 24 |     Creative --> Algo["Algorithm"]
 25 | ```
 26 | 
 27 | ## 🔄 LEVEL TRANSITION HANDLING
 28 | 
 29 | ```mermaid
 30 | graph TD
 31 |     L3["Level 3 Task"] --> Assess["Continuous<br>Assessment"]
 32 |     
 33 |     Assess --> Down["Downgrade to<br>Level 1/2"]
 34 |     Assess --> Up["Upgrade to<br>Level 4"]
 35 |     
 36 |     Down --> L12Trigger["Triggers:<br>- Simpler than expected<br>- Limited scope<br>- Few components"]
 37 |     
 38 |     Up --> L4Trigger["Triggers:<br>- System-wide impact<br>- Architectural changes<br>- High complexity"]
 39 |     
 40 |     L12Trigger --> L12Switch["Switch to<br>Level 1/2 Workflow"]
 41 |     L4Trigger --> L4Switch["Switch to<br>Level 4 Workflow"]
 42 | ```
 43 | 
 44 | ## 📋 PLANNING TEMPLATE
 45 | 
 46 | ```markdown
 47 | # Feature Planning Document
 48 | 
 49 | ## Requirements Analysis
 50 | - Core Requirements:
 51 |   - [ ] Requirement 1
 52 |   - [ ] Requirement 2
 53 | - Technical Constraints:
 54 |   - [ ] Constraint 1
 55 |   - [ ] Constraint 2
 56 | 
 57 | ## Component Analysis
 58 | - Affected Components:
 59 |   - Component 1
 60 |     - Changes needed:
 61 |     - Dependencies:
 62 |   - Component 2
 63 |     - Changes needed:
 64 |     - Dependencies:
 65 | 
 66 | ## Design Decisions
 67 | - Architecture:
 68 |   - [ ] Decision 1
 69 |   - [ ] Decision 2
 70 | - UI/UX:
 71 |   - [ ] Design 1
 72 |   - [ ] Design 2
 73 | - Algorithms:
 74 |   - [ ] Algorithm 1
 75 |   - [ ] Algorithm 2
 76 | 
 77 | ## Implementation Strategy
 78 | 1. Phase 1:
 79 |    - [ ] Task 1
 80 |    - [ ] Task 2
 81 | 2. Phase 2:
 82 |    - [ ] Task 3
 83 |    - [ ] Task 4
 84 | 
 85 | ## Testing Strategy
 86 | - Unit Tests:
 87 |   - [ ] Test 1
 88 |   - [ ] Test 2
 89 | - Integration Tests:
 90 |   - [ ] Test 3
 91 |   - [ ] Test 4
 92 | 
 93 | ## Documentation Plan
 94 | - [ ] API Documentation
 95 | - [ ] User Guide Updates
 96 | - [ ] Architecture Documentation
 97 | ```
 98 | 
 99 | ## 🎨 CREATIVE PHASE IDENTIFICATION
100 | 
101 | ```mermaid
102 | graph TD
103 |     subgraph "CREATIVE PHASES REQUIRED"
104 |     UI["🎨 UI/UX Design<br>Required: Yes/No"]
105 |     Arch["🏗️ Architecture Design<br>Required: Yes/No"]
106 |     Algo["⚙️ Algorithm Design<br>Required: Yes/No"]
107 |     end
108 |     
109 |     UI --> UITrig["Triggers:<br>- New UI Component<br>- UX Flow Change"]
110 |     Arch --> ArchTrig["Triggers:<br>- System Structure Change<br>- New Integration"]
111 |     Algo --> AlgoTrig["Triggers:<br>- Performance Critical<br>- Complex Logic"]
112 | ```
113 | 
114 | ## ✅ VERIFICATION CHECKLIST
115 | 
116 | ```mermaid
117 | graph TD
118 |     subgraph "PLANNING VERIFICATION"
119 |     R["Requirements<br>Complete"]
120 |     C["Components<br>Identified"]
121 |     D["Design Decisions<br>Made"]
122 |     I["Implementation<br>Plan Ready"]
123 |     T["Testing Strategy<br>Defined"]
124 |     Doc["Documentation<br>Plan Ready"]
125 |     end
126 |     
127 |     R --> C --> D --> I --> T --> Doc
128 | ```
129 | 
130 | ## 🔄 IMPLEMENTATION PHASES
131 | 
132 | ```mermaid
133 | graph LR
134 |     Setup["🛠️ Setup"] --> Core["⚙️ Core<br>Implementation"]
135 |     Core --> UI["🎨 UI<br>Implementation"]
136 |     UI --> Test["🧪 Testing"]
137 |     Test --> Doc["📚 Documentation"]
138 | ```
139 | 
140 | ## 🔄 INTEGRATION WITH MEMORY BANK
141 | 
142 | ```mermaid
143 | graph TD
144 |     L3["Level 3<br>Task"] --> PB["Comprehensive<br>projectbrief.md"]
145 |     L3 --> AC["Detailed<br>activeContext.md"]
146 |     L3 --> TM["Structured<br>tasks.md"]
147 |     L3 --> PM["Detailed<br>progress.md"]
148 |     
149 |     PB & AC & TM & PM --> MB["Memory Bank<br>Integration"]
150 |     MB --> NextPhase["Proceed to<br>Implementation"]
151 | ```
152 | 
153 | ## 🚨 PLANNING EFFICIENCY PRINCIPLE
154 | 
155 | Remember:
156 | 
157 | ```
158 | ┌─────────────────────────────────────────────────────┐
159 | │ Level 3 planning requires COMPREHENSIVE DESIGN but   │
160 | │ should avoid OVER-ENGINEERING. Focus on delivering  │
161 | │ maintainable, well-documented features.            │
162 | └─────────────────────────────────────────────────────┘
163 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Level3/reflection-intermediate.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: 
 3 | globs: reflection-intermediate.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # LEVEL 3 REFLECTION: INTERMEDIATE FEATURE REVIEW
 7 | 
 8 | > **TL;DR:** This guide structures the reflection process for a completed Level 3 intermediate feature. The focus is on a detailed review of the entire feature development lifecycle, from planning and design through implementation and testing, to extract meaningful lessons and identify improvements for future feature work.
 9 | 
10 | ## 🔍 Level 3 Reflection Process
11 | 
12 | The goal is to create a comprehensive `documentation\memory-bank/reflection/reflection-[feature_id].md` document.
13 | 
14 | ```mermaid
15 | graph TD
16 |     StartReflect["Start L3 Reflection"] -->
17 |     ReviewDocs["1. Review All Gathered Documentation"] -->
18 |     AssessOutcome["2. Assess Overall Feature Outcome<br>Did it meet all requirements from tasks.md? Was it successful?"] -->
19 |     AnalyzePlan["3. Analyze Planning Phase Effectiveness<br>Was planning-comprehensive.mdc guidance effective? Was the plan accurate? Scope creep?"] -->
20 |     AnalyzeCreative["4. Analyze Creative Phase(s) Effectiveness<br>Were design decisions sound? Did they translate well to implementation? Issues?"] -->
21 |     AnalyzeImpl["5. Analyze Implementation Phase<br>What went well? Challenges? Bottlenecks? Adherence to design/style guide?"] -->
22 |     AnalyzeTesting["6. Analyze Testing Phase<br>Were tests adequate? Bugs found post-release (if applicable)? Test coverage feel right?"] -->
23 |     IdentifyLessons["7. Identify Key Lessons Learned<br>(Technical, Process, Teamwork, Estimation)"] -->
24 |     ProposeImprovements["8. Propose Actionable Improvements<br>For future L3 feature development"] -->
25 |     DraftReflectionDoc["9. Draft `reflection-[feature_id].md`<br>Using structured template"] -->
26 |     FinalizeReflection["10. Finalize & Save Reflection Document"] -->
27 |     UpdateTasksStatus["11. Update `tasks.md`<br>Mark L3 Reflection Complete"] -->
28 |     ReflectionDone["L3 Reflection Complete<br>Ready for ARCHIVE Mode"]
29 | ````
30 | 
31 | ## 📝 Structure for `documentation\memory-bank/reflection-[feature_id].md`
32 | 
33 |   * **Feature Name & ID:**
34 |   * **Date of Reflection:**
35 |   * **Brief Feature Summary:** (What was built?)
36 |   * **1. Overall Outcome & Requirements Alignment:**
37 |       * How well did the final feature meet the initial requirements?
38 |       * Were there any deviations from the original scope? If so, why?
39 |       * What is the overall assessment of the feature's success?
40 |   * **2. Planning Phase Review:**
41 |       * How effective was the guidance from `Level3/planning-comprehensive.mdc`?
42 |       * Was the initial plan in `tasks.md` (component breakdown, strategy, risks) accurate and helpful?
43 |       * What could have been planned better? Were estimations (if made) accurate?
44 |   * **3. Creative Phase(s) Review (if applicable):**
45 |       * Were the right aspects flagged for CREATIVE mode?
46 |       * How effective were the design decisions made in `creative-*.md` documents?
47 |       * Did these designs translate well into practical implementation? Any friction points?
48 |       * Was `documentation\memory-bank/style-guide.md` clear and sufficient for UI aspects?
49 |   * **4. Implementation Phase Review:**
50 |       * What were the major successes during implementation? (e.g., efficient module development, good use of libraries)
51 |       * What were the biggest challenges or roadblocks? How were they overcome?
52 |       * Were there any unexpected technical difficulties or complexities?
53 |       * How was adherence to the style guide and coding standards?
54 |   * **5. Testing Phase Review:**
55 |       * Was the testing strategy (unit, integration, E2E for the feature) effective?
56 |       * Did testing uncover significant issues early enough?
57 |       * What could improve the testing process for similar features?
58 |   * **6. What Went Well? (Highlight 3-5 key positives across all phases for this feature)**
59 |   * **7. What Could Have Been Done Differently? (Identify 3-5 areas for improvement)**
60 |   * **8. Key Lessons Learned:**
61 |       * **Technical:** New insights about technologies, patterns, or architecture used for this feature.
62 |       * **Process:** Insights about the L3 workflow, communication, task management.
63 |       * **Estimation (if applicable):** Lessons about estimating work for features of this scale.
64 |   * **9. Actionable Improvements for Future L3 Features:** (Specific suggestions)
65 | 
66 | ## 🎯 Focus Areas for L3 Reflection
67 | 
68 |   * **Feature Scope Management:** Was the scope well-defined and managed?
69 |   * **Integration Complexity:** Challenges or successes in integrating the feature with the existing application.
70 |   * **Design-to-Implementation Fidelity:** How closely did the final product match the designs?
71 |   * **Cross-Component Impact:** Understanding the ripple effects of the feature.
72 | 


--------------------------------------------------------------------------------
/isolation_rules/Level3/task-tracking-intermediate.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: task tracking intermediate
  3 | globs: task-tracking-intermediate.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # LEVEL 3 INTERMEDIATE TASK TRACKING
  7 | 
  8 | > **TL;DR:** This document provides structured task tracking guidelines for Level 3 (Intermediate Feature) tasks, using visual tracking elements and clear checkpoints.
  9 | 
 10 | ## 🔍 TASK TRACKING WORKFLOW
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["Task Start"] --> Init["📋 Initialize<br>Task Entry"]
 15 |     Init --> Struct["🏗️ Create Task<br>Structure"]
 16 |     Struct --> Track["📊 Progress<br>Tracking"]
 17 |     Track --> Update["🔄 Regular<br>Updates"]
 18 |     Update --> Complete["✅ Task<br>Completion"]
 19 |     
 20 |     Struct --> Components["Components:"]
 21 |     Components --> Req["Requirements"]
 22 |     Components --> Steps["Implementation<br>Steps"]
 23 |     Components --> Creative["Creative Phase<br>Markers"]
 24 |     Components --> Check["Checkpoints"]
 25 |     
 26 |     Track --> Status["Track Status:"]
 27 |     Status --> InProg["🔄 In Progress"]
 28 |     Status --> Block["⛔ Blocked"]
 29 |     Status --> Done["✅ Complete"]
 30 |     Status --> Skip["⏭️ Skipped"]
 31 | ```
 32 | 
 33 | ## 📋 TASK ENTRY TEMPLATE
 34 | 
 35 | ```markdown
 36 | # [Task Title]
 37 | 
 38 | ## Requirements
 39 | - [ ] Requirement 1
 40 | - [ ] Requirement 2
 41 | - [ ] Requirement 3
 42 | 
 43 | ## Components Affected
 44 | - Component 1
 45 | - Component 2
 46 | - Component 3
 47 | 
 48 | ## Implementation Steps
 49 | 1. [ ] Step 1
 50 | 2. [ ] Step 2
 51 | 3. [ ] Step 3
 52 | 
 53 | ## Creative Phases Required
 54 | - [ ] 🎨 UI/UX Design
 55 | - [ ] 🏗️ Architecture Design
 56 | - [ ] ⚙️ Algorithm Design
 57 | 
 58 | ## Checkpoints
 59 | - [ ] Requirements verified
 60 | - [ ] Creative phases completed
 61 | - [ ] Implementation tested
 62 | - [ ] Documentation updated
 63 | 
 64 | ## Current Status
 65 | - Phase: [Current Phase]
 66 | - Status: [In Progress/Blocked/Complete]
 67 | - Blockers: [If any]
 68 | ```
 69 | 
 70 | ## 🔄 PROGRESS TRACKING VISUALIZATION
 71 | 
 72 | ```mermaid
 73 | graph TD
 74 |     subgraph "TASK PROGRESS"
 75 |     P1["✓ Requirements<br>Defined"]
 76 |     P2["✓ Components<br>Identified"]
 77 |     P3["→ Creative Phase<br>In Progress"]
 78 |     P4["□ Implementation"]
 79 |     P5["□ Testing"]
 80 |     P6["□ Documentation"]
 81 |     end
 82 | ```
 83 | 
 84 | ## ✅ UPDATE PROTOCOL
 85 | 
 86 | ```mermaid
 87 | sequenceDiagram
 88 |     participant Task as Task Entry
 89 |     participant Status as Status Update
 90 |     participant Creative as Creative Phase
 91 |     participant Implementation as Implementation
 92 |     
 93 |     Task->>Status: Update Progress
 94 |     Status->>Creative: Flag for Creative Phase
 95 |     Creative->>Implementation: Complete Design
 96 |     Implementation->>Status: Update Status
 97 |     Status->>Task: Mark Complete
 98 | ```
 99 | 
100 | ## 🎯 CHECKPOINT VERIFICATION
101 | 
102 | | Phase | Verification Items | Status |
103 | |-------|-------------------|--------|
104 | | Requirements | All requirements documented | [ ] |
105 | | Components | Affected components listed | [ ] |
106 | | Creative | Design decisions documented | [ ] |
107 | | Implementation | Code changes tracked | [ ] |
108 | | Testing | Test results recorded | [ ] |
109 | | Documentation | Updates completed | [ ] |
110 | 
111 | ## 🔄 DOCUMENT MANAGEMENT
112 | 
113 | ```mermaid
114 | graph TD
115 |     Current["Current Documents"] --> Active["Active:<br>- task-tracking-intermediate.md<br>- planning-comprehensive.md"]
116 |     Current --> Required["Required Next:<br>- creative-phase-enforcement.md<br>- implementation-phase-reference.md"]
117 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Phases/CreativePhase/creative-phase-architecture.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: creative phase architecture
  3 | globs: creative-phase-architecture.md
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # CREATIVE PHASE: ARCHITECTURE DESIGN
  8 | 
  9 | > **TL;DR:** This document provides structured guidance for architectural design decisions during creative phases, ensuring comprehensive evaluation of options and clear documentation of architectural choices.
 10 | 
 11 | ## 🏗️ ARCHITECTURE DESIGN WORKFLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["Architecture<br>Design Start"] --> Req["1. Requirements<br>Analysis"]
 16 |     Req --> Comp["2. Component<br>Identification"]
 17 |     Comp --> Options["3. Architecture<br>Options"]
 18 |     Options --> Eval["4. Option<br>Evaluation"]
 19 |     Eval --> Decision["5. Decision &<br>Documentation"]
 20 |     Decision --> Valid["6. Validation &<br>Verification"]
 21 | ```
 22 | 
 23 | ## 📋 ARCHITECTURE DECISION TEMPLATE
 24 | 
 25 | ```markdown
 26 | # Architecture Decision Record
 27 | 
 28 | ## Context
 29 | - System Requirements:
 30 |   - [Requirement 1]
 31 |   - [Requirement 2]
 32 | - Technical Constraints:
 33 |   - [Constraint 1]
 34 |   - [Constraint 2]
 35 | 
 36 | ## Component Analysis
 37 | - Core Components:
 38 |   - [Component 1]: [Purpose/Role]
 39 |   - [Component 2]: [Purpose/Role]
 40 | - Interactions:
 41 |   - [Interaction 1]
 42 |   - [Interaction 2]
 43 | 
 44 | **## 🧠 Architecture Options & MCP-Powered Research**
 45 | 
 46 | **Before finalizing options, use the DeepWiki MCP to gather data. For each potential library or framework, consider the following:**
 47 | 
 48 | - **`read_wiki_structure`**: Get a quick overview of the library's documentation.
 49 | - **`ask_question`**: Ask targeted questions like "What are the core architectural principles of this library?" or "How does this library handle state management compared to [alternative]?".
 50 | - **`read_wiki_contents`**: Pull full documentation for deep-dives on topics like "Performance" or "Security".
 51 | 
 52 | ### Option 1: [Name]
 53 | - Description: [Brief description]
 54 | - **MCP Insights**: [Summary of findings from MCP tools for this option]
 55 | - Pros:
 56 |   - [Pro 1]
 57 |   - [Pro 2]
 58 | - Cons:
 59 |   - [Con 1]
 60 |   - [Con 2]
 61 | - Technical Fit: [High/Medium/Low]
 62 | - Complexity: [High/Medium/Low]
 63 | - Scalability: [High/Medium/Low]
 64 | 
 65 | ### Option 2: [Name]
 66 | - Description: [Brief description]
 67 | - **MCP Insights**: [Summary of findings from MCP tools for this option]
 68 | [Same structure as Option 1]
 69 | 
 70 | ## Decision
 71 | - Chosen Option: [Option name]
 72 | - Rationale: [Explanation, referencing MCP insights where applicable]
 73 | - Implementation Considerations:
 74 |   - [Consideration 1]
 75 |   - [Consideration 2]
 76 | 
 77 | ## Validation
 78 | - Requirements Met:
 79 |   - [✓] Requirement 1
 80 |   - [✓] Requirement 2
 81 | - Technical Feasibility: [Assessment]
 82 | - Risk Assessment: [Evaluation]
 83 | ```
 84 | 
 85 | ## 🎯 ARCHITECTURE EVALUATION CRITERIA
 86 | 
 87 | ```mermaid
 88 | graph TD
 89 |     subgraph "EVALUATION CRITERIA"
 90 |     C1["Scalability"]
 91 |     C2["Maintainability"]
 92 |     C3["Performance"]
 93 |     C4["Security"]
 94 |     C5["Cost"]
 95 |     C6["Time to Market"]
 96 |     end
 97 | ```
 98 | 
 99 | ## 📊 ARCHITECTURE VISUALIZATION TEMPLATES
100 | 
101 | ### Component Diagram Template
102 | ```mermaid
103 | graph TD
104 |     subgraph "SYSTEM ARCHITECTURE"
105 |     C1["Component 1"]
106 |     C2["Component 2"]
107 |     C3["Component 3"]
108 |     
109 |     C1 -->|"Interface 1"| C2
110 |     C2 -->|"Interface 2"| C3
111 |     end
112 | ```
113 | 
114 | ### Data Flow Template
115 | ```mermaid
116 | sequenceDiagram
117 |     participant C1 as Component 1
118 |     participant C2 as Component 2
119 |     participant C3 as Component 3
120 |     
121 |     C1->>C2: Request
122 |     C2->>C3: Process
123 |     C3-->>C2: Response
124 |     C2-->>C1: Result
125 | ```
126 | 
127 | ## ✅ VERIFICATION CHECKLIST
128 | 
129 | ```markdown
130 | ## Architecture Design Verification
131 | - [ ] All system requirements addressed
132 | - [ ] Component responsibilities defined
133 | - [ ] Interfaces specified
134 | - [ ] Data flows documented
135 | - [ ] Security considerations addressed
136 | - [ ] Scalability requirements met
137 | - [ ] Performance requirements met
138 | - [ ] Maintenance approach defined
139 | 
140 | ## Implementation Readiness
141 | - [ ] All components identified
142 | - [ ] Dependencies mapped
143 | - [ ] Technical constraints documented
144 | - [ ] Risk assessment completed
145 | - [ ] Resource requirements defined
146 | - [ ] Timeline estimates provided
147 | ```
148 | 
149 | ## 🔄 ARCHITECTURE REVIEW PROCESS
150 | 
151 | ```mermaid
152 | graph TD
153 |     subgraph "REVIEW PROCESS"
154 |     R1["Technical<br>Review"]
155 |     R2["Security<br>Review"]
156 |     R3["Performance<br>Review"]
157 |     R4["Final<br>Approval"]
158 |     end
159 |     
160 |     R1 --> R2 --> R3 --> R4
161 | ```
162 | 
163 | ## 🔄 DOCUMENT MANAGEMENT
164 | 
165 | ```mermaid
166 | graph TD
167 |     Current["Current Document"] --> Active["Active:<br>- creative-phase-architecture.md"]
168 |     Current --> Related["Related:<br>- creative-phase-enforcement.md<br>- planning-comprehensive.md"]
169 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/Phases/CreativePhase/optimized-creative-template.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Optimized creative phase template with progressive documentation
  3 | globs: "**/creative*/**", "**/design*/**", "**/decision*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # OPTIMIZED CREATIVE PHASE TEMPLATE
  8 | 
  9 | > **TL;DR:** This template implements a progressive documentation approach for creative phases, optimizing token usage while maintaining thorough design exploration.
 10 | 
 11 | ## 📝 PROGRESSIVE DOCUMENTATION MODEL
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["Creative Phase Start"] --> P1["1️⃣ PROBLEM<br>Define scope"]
 16 |     P1 --> P2["2️⃣ OPTIONS<br>Explore alternatives"]
 17 |     P2 --> P3["3️⃣ ANALYSIS<br>Evaluate selected options"]
 18 |     P3 --> P4["4️⃣ DECISION<br>Finalize approach"]
 19 |     P4 --> P5["5️⃣ IMPLEMENTATION<br>Document guidelines"]
 20 | ```
 21 | 
 22 | ## 📋 TEMPLATE STRUCTURE
 23 | 
 24 | ```markdown
 25 | 📌 CREATIVE PHASE START: [Component Name]
 26 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 27 | 
 28 | 1️⃣ PROBLEM
 29 |    Description: [Brief problem description]
 30 |    Requirements: [Key requirements as bullet points]
 31 |    Constraints: [Technical or business constraints]
 32 | 
 33 | 2️⃣ OPTIONS
 34 |    Option A: [Name] - [One-line description]
 35 |    Option B: [Name] - [One-line description]
 36 |    Option C: [Name] - [One-line description]
 37 | 
 38 | 3️⃣ ANALYSIS
 39 |    | Criterion | Option A | Option B | Option C |
 40 |    |-----------|----------|----------|----------|
 41 |    | Performance | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐ |
 42 |    | Complexity | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
 43 |    | Maintainability | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ |
 44 |    
 45 |    Key Insights:
 46 |    - [Insight 1]
 47 |    - [Insight 2]
 48 | 
 49 | 4️⃣ DECISION
 50 |    Selected: [Option X]
 51 |    Rationale: [Brief justification]
 52 |    
 53 | 5️⃣ IMPLEMENTATION NOTES
 54 |    - [Implementation note 1]
 55 |    - [Implementation note 2]
 56 |    - [Implementation note 3]
 57 | 
 58 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 59 | 📌 CREATIVE PHASE END
 60 | ```
 61 | 
 62 | ## 🧩 DETAILED OPTION ANALYSIS (ON DEMAND)
 63 | 
 64 | Detailed analysis can be provided on demand for selected options:
 65 | 
 66 | ```markdown
 67 | <details>
 68 |   <summary>Detailed Analysis: Option A</summary>
 69 |   
 70 |   ### Option A: [Full Name]
 71 |   
 72 |   **Complete Description**:
 73 |   [Detailed description of how the option works]
 74 |   
 75 |   **Pros**:
 76 |   - [Pro 1 with explanation]
 77 |   - [Pro 2 with explanation]
 78 |   - [Pro 3 with explanation]
 79 |   
 80 |   **Cons**:
 81 |   - [Con 1 with explanation]
 82 |   - [Con 2 with explanation]
 83 |   
 84 |   **Implementation Complexity**: [Low/Medium/High]
 85 |   [Explanation of complexity factors]
 86 |   
 87 |   **Resource Requirements**:
 88 |   [Details on resource needs]
 89 |   
 90 |   **Risk Assessment**:
 91 |   [Analysis of risks]
 92 | </details>
 93 | ```
 94 | 
 95 | ## 📊 COMPLEXITY-BASED SCALING
 96 | 
 97 | The template automatically scales documentation requirements based on task complexity level:
 98 | 
 99 | ### Level 1-2 (Quick Fix/Enhancement)
100 | - Simplified problem/solution
101 | - Focus on implementation
102 | - Minimal option exploration
103 | 
104 | ### Level 3 (Feature Development)
105 | - Multiple options required
106 | - Analysis table with key criteria
107 | - Implementation guidelines
108 | 
109 | ### Level 4 (Enterprise Development)
110 | - Comprehensive analysis
111 | - Multiple viewpoints considered
112 | - Detailed implementation plan
113 | - Expanded verification criteria
114 | 
115 | ## ✅ VERIFICATION PROTOCOL
116 | 
117 | Quality verification is condensed into a simple checklist:
118 | 
119 | ```markdown
120 | VERIFICATION:
121 | [x] Problem clearly defined
122 | [x] Multiple options considered
123 | [x] Decision made with rationale
124 | [x] Implementation guidance provided
125 | ```
126 | 
127 | ## 🔄 USAGE EXAMPLES
128 | 
129 | ### Architecture Decision (Level 3)
130 | 
131 | ```markdown
132 | 📌 CREATIVE PHASE START: Authentication System
133 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
134 | 
135 | 1️⃣ PROBLEM
136 |    Description: Design an authentication system for the application
137 |    Requirements: Secure, scalable, supports SSO, easy to maintain
138 |    Constraints: Must work with existing user database, <100ms response time
139 | 
140 | 2️⃣ OPTIONS
141 |    Option A: JWT-based stateless auth - Simple token-based approach
142 |    Option B: Session-based auth with Redis - Server-side session storage
143 |    Option C: OAuth2 implementation - Delegated authorization framework
144 | 
145 | 3️⃣ ANALYSIS
146 |    | Criterion | JWT | Sessions | OAuth2 |
147 |    |-----------|-----|----------|--------|
148 |    | Security | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
149 |    | Scalability | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
150 |    | Complexity | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
151 |    | Performance | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
152 |    
153 |    Key Insights:
154 |    - JWT offers best performance but limited revocation options
155 |    - Sessions provide better security control but require more infrastructure
156 |    - OAuth2 most complex but offers best integration possibilities
157 | 
158 | 4️⃣ DECISION
159 |    Selected: Option A: JWT-based auth with refresh tokens
160 |    Rationale: Best balance of performance and scalability while meeting security needs
161 |    
162 | 5️⃣ IMPLEMENTATION NOTES
163 |    - Use HS256 algorithm for token signing
164 |    - Implement short-lived access tokens (15min) with longer refresh tokens (7 days)
165 |    - Store token blacklist in Redis for revocation capability
166 |    - Add rate limiting on token endpoints
167 | 
168 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
169 | 📌 CREATIVE PHASE END
170 | ```
171 | 
172 | ### Algorithm Decision (Level 2)
173 | 
174 | ```markdown
175 | 📌 CREATIVE PHASE START: Search Algorithm
176 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
177 | 
178 | 1️⃣ PROBLEM
179 |    Description: Implement efficient text search for product catalog
180 |    Requirements: Fast results, support for partial matches, case insensitive
181 |    Constraints: Dataset < 10,000 items, must work in browser environment
182 | 
183 | 2️⃣ OPTIONS
184 |    Option A: Simple regex search - Basic pattern matching
185 |    Option B: Trie-based search - Prefix tree structure
186 |    Option C: Fuzzy search with Levenshtein - Edit distance algorithm
187 | 
188 | 3️⃣ DECISION
189 |    Selected: Option B: Trie-based search
190 |    Rationale: Best performance for prefix searches with manageable memory usage
191 |    
192 | 4️⃣ IMPLEMENTATION NOTES
193 |    - Use existing trie library
194 |    - Preprocess text to lowercase during indexing
195 |    - Implement letter-by-letter search for instant results
196 |    - Add debounce (300ms) to prevent excessive rebuilding
197 | 
198 | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
199 | 📌 CREATIVE PHASE END
200 | ```
201 | 
202 | ## 🏆 TOKEN EFFICIENCY BENEFITS
203 | 
204 | This template significantly reduces token usage by:
205 | 
206 | 1. Focusing on essential information without unnecessary verbosity
207 | 2. Using compact tabular formats for comparisons
208 | 3. Implementing progressive disclosure for detailed information
209 | 4. Scaling documentation requirements by task complexity
210 | 5. Using visual indicators (emojis) for quick scanning
211 | 
212 | The template maintains the rigor of the creative process while improving token efficiency by approximately 60% over the previous format.


--------------------------------------------------------------------------------
/isolation_rules/main-optimized.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Optimized main rule for improved token efficiency
  3 | globs: main-optimized.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # 🔍 OPTIMIZED MEMORY BANK SYSTEM
  7 | 
  8 | 🚨 CRITICAL RULE: MEMORY BANK CREATION IS MANDATORY 🚨
  9 | Memory Bank MUST be created BEFORE any other operation in ANY mode
 10 | NO process can continue without verifying Memory Bank existence
 11 | 
 12 | > **TL;DR:** This system uses optimized context management and adaptive rule loading to maximize token efficiency while preserving the structured development approach.
 13 | 
 14 | ## 🧭 OPTIMIZED MODE ARCHITECTURE
 15 | 
 16 | ```mermaid
 17 | graph TD
 18 |     subgraph "Memory Bank Core"
 19 |         Context["Context Manager"]
 20 |         Rules["Rule Loader"]
 21 |         FileIO["File Manager"]
 22 |         Transition["Mode Transition"]
 23 |     end
 24 |     
 25 |     subgraph "Custom Modes"
 26 |         VAN["VAN<br>Initialization"]
 27 |         PLAN["PLAN<br>Planning"]
 28 |         CREATIVE["CREATIVE<br>Design"]
 29 |         IMPLEMENT["IMPLEMENT<br>Building"]
 30 |         REFLECT["REFLECT<br>Review"]
 31 |         ARCHIVE["ARCHIVE<br>Documentation"]
 32 |     end
 33 |     
 34 |     Context --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
 35 |     Rules --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
 36 |     FileIO --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
 37 |     Transition --> VAN & PLAN & CREATIVE & IMPLEMENT & REFLECT & ARCHIVE
 38 |     
 39 |     VAN --> PLAN
 40 |     PLAN --> CREATIVE
 41 |     CREATIVE --> IMPLEMENT
 42 |     IMPLEMENT --> REFLECT
 43 |     REFLECT --> ARCHIVE
 44 | ```
 45 | 
 46 | ## 📈 ADAPTIVE COMPLEXITY MODEL
 47 | 
 48 | ```mermaid
 49 | graph TD
 50 |     Task["Task Creation"] --> Complexity{"Complexity<br>Level?"}
 51 |     
 52 |     Complexity -->|"Level 1<br>Quick Fix"| L1["3-Phase<br>Streamlined Process"]
 53 |     Complexity -->|"Level 2<br>Enhancement"| L2["4-Phase<br>Balanced Process"]
 54 |     Complexity -->|"Level 3<br>Feature"| L3["5-Phase<br>Comprehensive Process"]
 55 |     Complexity -->|"Level 4<br>Enterprise"| L4["6-Phase<br>Governance Process"]
 56 |     
 57 |     L1 --> L1_Process["VAN → IMPLEMENT → REFLECT"]
 58 |     L2 --> L2_Process["VAN → PLAN → IMPLEMENT → REFLECT"]
 59 |     L3 --> L3_Process["VAN → PLAN → CREATIVE → IMPLEMENT → REFLECT"]
 60 |     L4 --> L4_Process["VAN → PLAN → CREATIVE → IMPLEMENT → REFLECT → ARCHIVE"]
 61 | ```
 62 | 
 63 | ## 🧠 HIERARCHICAL RULE LOADING
 64 | 
 65 | Rules are loaded hierarchically to optimize context usage:
 66 | 
 67 | ```mermaid
 68 | graph TD
 69 |     Root["Memory Bank<br>Common Rules"] --> Core["Core Rules<br>Shared Across Modes"]
 70 |     
 71 |     Core --> L1["Level 1<br>Rules"]
 72 |     Core --> L2["Level 2<br>Rules"]
 73 |     Core --> L3["Level 3<br>Rules"]
 74 |     Core --> L4["Level 4<br>Rules"]
 75 |     
 76 |     Core --> VM["Mode<br>Visual Maps"]
 77 |     
 78 |     Core --> Phase["Phase-Specific<br>Rules"]
 79 |     
 80 |     Phase --> VAN_Rules["VAN Mode<br>Rules"]
 81 |     Phase --> PLAN_Rules["PLAN Mode<br>Rules"]
 82 |     Phase --> CREATIVE_Rules["CREATIVE Mode<br>Rules"]
 83 |     Phase --> IMPLEMENT_Rules["IMPLEMENT Mode<br>Rules"]
 84 |     Phase --> REFLECT_Rules["REFLECT Mode<br>Rules"]
 85 |     Phase --> ARCHIVE_Rules["ARCHIVE Mode<br>Rules"]
 86 | ```
 87 | 
 88 | ## 🔄 TOKEN-OPTIMIZED CREATIVE PHASE
 89 | 
 90 | Creative phase documentation is progressively generated:
 91 | 
 92 | ```mermaid
 93 | graph TD
 94 |     Start["Creative Phase<br>Initiation"] --> P1["1️⃣ PROBLEM<br>Define scope"]
 95 |     P1 --> P2["2️⃣ OPTIONS<br>List alternatives"]
 96 |     P2 --> P3["3️⃣ ANALYSIS<br>Compare options"]
 97 |     P3 --> P4["4️⃣ DECISION<br>Select approach"]
 98 |     P4 --> P5["5️⃣ GUIDELINES<br>Document implementation"]
 99 |     
100 |     P3 -.->|"On Demand"| Details["Detailed Option<br>Analysis"]
101 |     
102 | ```
103 | 
104 | ## 🔀 OPTIMIZED MODE TRANSITIONS
105 | 
106 | Mode transitions use a unified context transfer protocol:
107 | 
108 | ```mermaid
109 | sequenceDiagram
110 |     participant Current as Current Mode
111 |     participant Context as Context Manager
112 |     participant Next as Next Mode
113 |     
114 |     Current->>Context: Create transition document
115 |     Current->>Context: Store critical context
116 |     Context->>Context: Prepare rule cache
117 |     Current->>Next: Initiate transition
118 |     Next->>Context: Verify context availability
119 |     Context->>Next: Load relevant context
120 |     Context->>Next: Load cached rules
121 |     Next->>Next: Continue with preserved context
122 | ```
123 | 
124 | ## 📊 MEMORY BANK EFFICIENT UPDATES
125 | 
126 | ```mermaid
127 | graph TD
128 |     subgraph "Memory Bank Files"
129 |         tasks["tasks.md<br>Source of Truth"]
130 |         active["activeContext.md<br>Current Focus"]
131 |         creative["creative-*.md<br>Design Decisions"]
132 |         progress["progress.md<br>Implementation Status"]
133 |         transition["transition.md<br>Mode Transitions"]
134 |     end
135 |     
136 |     Update["Update Request"] --> Diff{"Changed?"}
137 |     Diff -->|"No"| Skip["Skip Update"]
138 |     Diff -->|"Yes"| Section{"Section<br>Change?"}
139 |     Section -->|"Yes"| Partial["Update Changed<br>Sections Only"]
140 |     Section -->|"No"| Full["Full File<br>Update"]
141 |     
142 |     Partial --> tasks
143 |     Full --> tasks
144 | 
145 | ```
146 | 
147 | ## 💻 COMPLEXITY-BASED DOCUMENTATION
148 | 
149 | Documentation requirements scale based on complexity level:
150 | 
151 | | Documentation | Level 1 | Level 2 | Level 3 | Level 4 |
152 | |---------------|---------|---------|---------|---------|
153 | | Problem Definition | Brief | Standard | Detailed | Comprehensive |
154 | | Options Analysis | Optional | Basic | Multiple Options | Extensive |
155 | | Implementation Plan | Simple | Standard | Detailed | Phased |
156 | | Testing Requirements | Basic | Standard | Comprehensive | Rigorous |
157 | | Documentation | Minimal | Standard | Detailed | Extensive |
158 | 
159 | ## 📑 OPTIMIZED TEMPLATES BY LEVEL
160 | 
161 | ### Level 1: Quick Fix Template
162 | ```markdown
163 | ## QUICK FIX: [Issue Name]
164 | - Problem: [Brief description]
165 | - Solution: [Implemented approach]
166 | - Verification: [How fix was tested]
167 | ```
168 | 
169 | ### Level 2: Enhancement Template
170 | ```markdown
171 | ## ENHANCEMENT: [Feature Name]
172 | - Requirement: [What needs to be done]
173 | - Approach: [How it was implemented]
174 | - Testing: [Verification approach]
175 | - Documentation: [Where documented]
176 | ```
177 | 
178 | ### Level 3-4: Comprehensive Template
179 | Uses the optimized creative phase template with appropriate documentation depth
180 | 
181 | ## 🔄 REFERENCE MAPS
182 | 
183 | Each mode's visual process map is optimized for token efficiency:
184 | 
185 | - @VAN Mode Map (Optimized)
186 | - @PLAN Mode Map (Optimized)
187 | - @CREATIVE Mode Map (Optimized)
188 | - @IMPLEMENT Mode Map (Optimized)
189 | - @REFLECT Mode Map (Optimized)
190 | - @ARCHIVE Mode Map (Optimized)
191 | 
192 | ## ⚡ TOKEN EFFICIENCY IMPROVEMENTS
193 | 
194 | Optimizations in this version:
195 | 
196 | 1. Hierarchical rule loading (65% token reduction)
197 | 2. Progressive creative phase documentation (60% token reduction)
198 | 3. Context preservation during mode transitions (40% token reduction)
199 | 4. Differential Memory Bank updates (30% token reduction)
200 | 5. Complexity-based template scaling (varies by level)
201 | 
202 | ## 💡 USAGE GUIDANCE
203 | 
204 | To use the optimized system:
205 | 
206 | 1. Start with the VAN command to initialize and determine complexity
207 | 2. Follow the complexity-appropriate workflow
208 | 3. Use progressive documentation appropriate to task complexity
209 | 4. Let the system manage rule loading and context preservation
210 | 5. Enjoy the improved token efficiency while maintaining structured development


--------------------------------------------------------------------------------
/isolation_rules/main.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: main rule
  3 | globs: main.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # 🔍 ISOLATION-FOCUSED MEMORY BANK SYSTEM
  7 | 
  8 | 🚨 CRITICAL RULE: MEMORY BANK CREATION IS MANDATORY 🚨
  9 | Memory Bank MUST be created BEFORE any other operation in ANY mode
 10 | NO process can continue without verifying Memory Bank existence
 11 | 
 12 | > **TL;DR:** This system is designed to work with Cursor custom modes, where each mode loads only the rules it needs. The system uses visual Mermaid diagrams and selective document loading to optimize context usage.
 13 | 
 14 | ## 🧭 MODE-SPECIFIC VISUAL MAPS
 15 | 
 16 | ```mermaid
 17 | graph TD
 18 |     subgraph Modes["Cursor Custom Modes"]
 19 |         VAN["VAN MODE<br>Initialization"] --> PLAN["PLAN MODE<br>Task Planning"]
 20 |         PLAN --> Creative["CREATIVE MODE<br>Design Decisions"]
 21 |         Creative --> Implement["IMPLEMENT MODE<br>Code Implementation"]
 22 |         Implement --> Reflect["REFLECT MODE<br>Task Review"]
 23 |         Reflect --> Archive["ARCHIVE MODE<br>Documentation"]
 24 |     end
 25 |     
 26 |     VAN -.->|"Loads"| VANRules["• main.md<br>• platform-awareness.md<br>• file-verification.md<br>• workflow-init.md"]
 27 |     PLAN -.->|"Loads"| PLANRules["• main.md<br>• task-tracking.md<br>• planning-process.md"]
 28 |     Creative -.->|"Loads"| CreativeRules["• main.md<br>• creative-phase.md<br>• design-patterns.md"]
 29 |     Implement -.->|"Loads"| ImplementRules["• main.md<br>• command-execution.md<br>• implementation-guide.md"]
 30 |     Reflect -.->|"Loads"| ReflectRules["• main.md<br>• reflection-format.md"]
 31 |     Archive -.->|"Loads"| ArchiveRules["• main.md<br>• archiving-guide.md"]
 32 | ```
 33 | 
 34 | ## 📋 MEMORY BANK VERIFICATION - MANDATORY IN ALL MODES
 35 | 
 36 | ```mermaid
 37 | graph TD
 38 |     Start["Mode Activation"] --> CheckMemBank{"Memory Bank<br>Exists?"}
 39 |     
 40 |     CheckMemBank -->|"No"| CreateMemBank["CREATE MEMORY BANK<br>[CRITICAL STEP]"]
 41 |     CheckMemBank -->|"Yes"| VerifyMemBank["Verify Memory Bank<br>Structure"]
 42 |     
 43 |     CreateMemBank --> VerifyCreation{"Creation<br>Successful?"}
 44 |     VerifyCreation -->|"No"| AbortAll["⛔ ABORT ALL OPERATIONS<br>Fix Memory Bank First"]
 45 |     VerifyCreation -->|"Yes"| VerifyMemBank
 46 |     
 47 |     VerifyMemBank --> StructureCheck{"Structure<br>Valid?"}
 48 |     StructureCheck -->|"No"| FixStructure["Fix Memory Bank<br>Structure"]
 49 |     StructureCheck -->|"Yes"| ContinueMode["Continue with<br>Mode Operations"]
 50 |     
 51 |     FixStructure --> VerifyFix{"Fix<br>Successful?"}
 52 |     VerifyFix -->|"No"| AbortAll
 53 |     VerifyFix -->|"Yes"| ContinueMode
 54 | ```
 55 | 
 56 | ## 📚 VISUAL PROCESS MAPS
 57 | 
 58 | Each mode has its own visual process map:
 59 | 
 60 | - @VAN Mode Map
 61 | - @PLAN Mode Map
 62 | - @CREATIVE Mode Map
 63 | - @IMPLEMENT Mode Map
 64 | - @REFLECT Mode Map
 65 | - @ARCHIVE Mode Map
 66 | 
 67 | ## 🔄 FILE STATE VERIFICATION
 68 | 
 69 | In this isolation-focused approach, Memory Bank files maintain continuity between modes:
 70 | 
 71 | ```mermaid
 72 | graph TD
 73 |     subgraph "Memory Bank Files"
 74 |         tasks["tasks.md<br>Source of Truth"]
 75 |         active["activeContext.md<br>Current Focus"]
 76 |         creative["creative-*.md<br>Design Decisions"]
 77 |         progress["progress.md<br>Implementation Status"]
 78 |     end
 79 |     
 80 |     VAN["VAN MODE"] -->|"Creates/Updates"| tasks
 81 |     VAN -->|"Creates/Updates"| active
 82 |     
 83 |     PLAN["PLAN MODE"] -->|"Reads"| tasks
 84 |     PLAN -->|"Reads"| active
 85 |     PLAN -->|"Updates"| tasks
 86 |     
 87 |     Creative["CREATIVE MODE"] -->|"Reads"| tasks
 88 |     Creative -->|"Creates"| creative
 89 |     Creative -->|"Updates"| tasks
 90 |     
 91 |     Implement["IMPLEMENT MODE"] -->|"Reads"| tasks
 92 |     Implement -->|"Reads"| creative
 93 |     Implement -->|"Updates"| tasks
 94 |     Implement -->|"Updates"| progress
 95 |     
 96 |     Reflect["REFLECT MODE"] -->|"Reads"| tasks
 97 |     Reflect -->|"Reads"| progress
 98 |     Reflect -->|"Updates"| tasks
 99 |     
100 |     Archive["ARCHIVE MODE"] -->|"Reads"| tasks
101 |     Archive -->|"Reads"| progress
102 |     Archive -->|"Archives"| creative
103 | ```
104 | 
105 | ## 📋 MODE TRANSITION PROTOCOL
106 | 
107 | ```mermaid
108 | sequenceDiagram
109 |     participant User
110 |     participant CurrentMode
111 |     participant NextMode
112 |     
113 |     CurrentMode->>CurrentMode: Complete Phase Requirements
114 |     CurrentMode->>User: "Phase complete. NEXT MODE: [mode name]"
115 |     User->>CurrentMode: End Current Mode
116 |     User->>NextMode: Start Next Mode
117 |     NextMode->>NextMode: Verify Required File State
118 |     
119 |     alt File State Valid
120 |         NextMode->>User: "Continuing from previous mode..."
121 |     else File State Invalid
122 |         NextMode->>User: "Required files not in expected state"
123 |         NextMode->>User: "Return to [previous mode] to complete requirements"
124 |     end
125 | ```
126 | 
127 | ## 💻 PLATFORM-SPECIFIC COMMANDS
128 | 
129 | | Action | Windows | Mac/Linux |
130 | |--------|---------|-----------|
131 | | Create file | `echo. > file.ext` | `touch file.ext` |
132 | | Create directory | `mkdir directory` | `mkdir -p directory` |
133 | | Change directory | `cd directory` | `cd directory` |
134 | | List files | `dir` | `ls` |
135 | | Show file content | `type file.ext` | `cat file.ext` |
136 | 
137 | ## ⚠️ COMMAND EFFICIENCY GUIDANCE
138 | 
139 | For optimal performance, use efficient command chaining when appropriate:
140 | 
141 | ```
142 | # Efficient command chaining examples:
143 | mkdir -p project/{src,tests,docs} && cd project
144 | grep "TODO" $(find . -name "*.js")
145 | npm install && npm start
146 | ```
147 | 
148 | Refer to [command-execution.mdc](mdc:.cursor/rules/isolation_rules/Core/command-execution.mdc) for detailed guidance. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/archive-mode-map.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for ARCHIVE mode (Task Documentation)
  3 | globs: "**/archive*/**", "**/document*/**", "**/complete*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # ARCHIVE MODE: TASK DOCUMENTATION PROCESS MAP
  8 | 
  9 | > **TL;DR:** This visual map guides the ARCHIVE mode process, focusing on creating comprehensive documentation of the completed task, archiving relevant files, and updating the Memory Bank for future reference.
 10 | 
 11 | ## 🧭 ARCHIVE MODE PROCESS FLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["START ARCHIVE MODE"] --> ReadTasks["Read tasks.md<br>reflection.md and<br>progress.md"]
 16 |     
 17 |     %% Initial Assessment
 18 |     ReadTasks --> VerifyReflect{"Reflection<br>Complete?"}
 19 |     VerifyReflect -->|"No"| ReturnReflect["Return to<br>REFLECT Mode"]
 20 |     VerifyReflect -->|"Yes"| AssessLevel{"Determine<br>Complexity Level"}
 21 |     
 22 |     %% Level-Based Archiving
 23 |     AssessLevel -->|"Level 1"| L1Archive["LEVEL 1 ARCHIVING<br>Level1/archive-minimal.md"]
 24 |     AssessLevel -->|"Level 2"| L2Archive["LEVEL 2 ARCHIVING<br>Level2/archive-basic.md"]
 25 |     AssessLevel -->|"Level 3"| L3Archive["LEVEL 3 ARCHIVING<br>Level3/archive-standard.md"]
 26 |     AssessLevel -->|"Level 4"| L4Archive["LEVEL 4 ARCHIVING<br>Level4/archive-comprehensive.md"]
 27 |     
 28 |     %% Level 1 Archiving (Minimal)
 29 |     L1Archive --> L1Summary["Create Quick<br>Summary"]
 30 |     L1Summary --> L1Task["Update<br>tasks.md"]
 31 |     L1Task --> L1Complete["Mark Task<br>Complete"]
 32 |     
 33 |     %% Level 2 Archiving (Basic)
 34 |     L2Archive --> L2Summary["Create Basic<br>Archive Document"]
 35 |     L2Summary --> L2Doc["Document<br>Changes"]
 36 |     L2Doc --> L2Task["Update<br>tasks.md"]
 37 |     L2Task --> L2Progress["Update<br>progress.md"]
 38 |     L2Progress --> L2Complete["Mark Task<br>Complete"]
 39 |     
 40 |     %% Level 3-4 Archiving (Comprehensive)
 41 |     L3Archive & L4Archive --> L34Summary["Create Comprehensive<br>Archive Document"]
 42 |     L34Summary --> L34Doc["Document<br>Implementation"]
 43 |     L34Doc --> L34Creative["Archive Creative<br>Phase Documents"]
 44 |     L34Creative --> L34Code["Document Code<br>Changes"]
 45 |     L34Code --> L34Test["Document<br>Testing"]
 46 |     L34Test --> L34Lessons["Summarize<br>Lessons Learned"]
 47 |     L34Lessons --> L34Task["Update<br>tasks.md"]
 48 |     L34Task --> L34Progress["Update<br>progress.md"]
 49 |     L34Progress --> L34System["Update System<br>Documentation"]
 50 |     L34System --> L34Complete["Mark Task<br>Complete"]
 51 |     
 52 |     %% Completion
 53 |     L1Complete & L2Complete & L34Complete --> CreateArchive["Create Archive<br>Document in<br>docs/archive/"]
 54 |     CreateArchive --> UpdateActive["Update<br>activeContext.md"]
 55 |     UpdateActive --> Reset["Reset for<br>Next Task"]
 56 | ```
 57 | 
 58 | ## 📋 ARCHIVE DOCUMENT STRUCTURE
 59 | 
 60 | The archive document should follow this structured format:
 61 | 
 62 | ```mermaid
 63 | graph TD
 64 |     subgraph "Archive Document Structure"
 65 |         Header["# TASK ARCHIVE: [Task Name]"]
 66 |         Meta["## METADATA<br>Task info, dates, complexity"]
 67 |         Summary["## SUMMARY<br>Brief overview of the task"]
 68 |         Requirements["## REQUIREMENTS<br>What the task needed to accomplish"]
 69 |         Implementation["## IMPLEMENTATION<br>How the task was implemented"]
 70 |         Testing["## TESTING<br>How the solution was verified"]
 71 |         Lessons["## LESSONS LEARNED<br>Key takeaways from the task"]
 72 |         Refs["## REFERENCES<br>Links to related documents"]
 73 |     end
 74 |     
 75 |     Header --> Meta --> Summary --> Requirements --> Implementation --> Testing --> Lessons --> Refs
 76 | ```
 77 | 
 78 | ## 📊 REQUIRED FILE STATE VERIFICATION
 79 | 
 80 | Before archiving can begin, verify file state:
 81 | 
 82 | ```mermaid
 83 | graph TD
 84 |     Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>reflection<br>complete?"}
 85 |     
 86 |     CheckTasks -->|"No"| ErrorReflect["ERROR:<br>Return to REFLECT Mode"]
 87 |     CheckTasks -->|"Yes"| CheckReflection{"reflection.md<br>exists?"}
 88 |     
 89 |     CheckReflection -->|"No"| ErrorCreate["ERROR:<br>Create reflection.md first"]
 90 |     CheckReflection -->|"Yes"| CheckProgress{"progress.md<br>updated?"}
 91 |     
 92 |     CheckProgress -->|"No"| ErrorProgress["ERROR:<br>Update progress.md first"]
 93 |     CheckProgress -->|"Yes"| ReadyArchive["Ready for<br>Archiving"]
 94 | ```
 95 | 
 96 | ## 🔍 ARCHIVE TYPES BY COMPLEXITY
 97 | 
 98 | ```mermaid
 99 | graph TD
100 |     subgraph "Level 1: Minimal Archive"
101 |         L1A["Basic Bug<br>Description"]
102 |         L1B["Solution<br>Summary"]
103 |         L1C["Affected<br>Files"]
104 |     end
105 |     
106 |     subgraph "Level 2: Basic Archive"
107 |         L2A["Enhancement<br>Description"]
108 |         L2B["Implementation<br>Summary"]
109 |         L2C["Testing<br>Results"]
110 |         L2D["Lessons<br>Learned"]
111 |     end
112 |     
113 |     subgraph "Level 3-4: Comprehensive Archive"
114 |         L3A["Detailed<br>Requirements"]
115 |         L3B["Architecture/<br>Design Decisions"]
116 |         L3C["Implementation<br>Details"]
117 |         L3D["Testing<br>Strategy"]
118 |         L3E["Performance<br>Considerations"]
119 |         L3F["Future<br>Enhancements"]
120 |         L3G["Cross-References<br>to Other Systems"]
121 |     end
122 |     
123 |     L1A --> L1B --> L1C
124 |     
125 |     L2A --> L2B --> L2C --> L2D
126 |     
127 |     L3A --> L3B --> L3C --> L3D --> L3E --> L3F --> L3G
128 | ```
129 | 
130 | ## 📝 ARCHIVE DOCUMENT TEMPLATES
131 | 
132 | ### Level 1 (Minimal) Archive
133 | ```
134 | # Bug Fix Archive: [Bug Name]
135 | 
136 | ## Date
137 | [Date of fix]
138 | 
139 | ## Summary
140 | [Brief description of the bug and solution]
141 | 
142 | ## Implementation
143 | [Description of the fix implemented]
144 | 
145 | ## Files Changed
146 | - [File 1]
147 | - [File 2]
148 | ```
149 | 
150 | ### Levels 2-4 (Comprehensive) Archive
151 | ```
152 | # Task Archive: [Task Name]
153 | 
154 | ## Metadata
155 | - **Complexity**: Level [2/3/4]
156 | - **Type**: [Enhancement/Feature/System]
157 | - **Date Completed**: [Date]
158 | - **Related Tasks**: [Related task references]
159 | 
160 | ## Summary
161 | [Comprehensive summary of the task]
162 | 
163 | ## Requirements
164 | - [Requirement 1]
165 | - [Requirement 2]
166 | - [Requirement 3]
167 | 
168 | ## Implementation
169 | ### Approach
170 | [Description of implementation approach]
171 | 
172 | ### Key Components
173 | - [Component 1]: [Description]
174 | - [Component 2]: [Description]
175 | 
176 | ### Files Changed
177 | - [File 1]: [Description of changes]
178 | - [File 2]: [Description of changes]
179 | 
180 | ## Testing
181 | - [Test 1]: [Result]
182 | - [Test 2]: [Result]
183 | 
184 | ## Lessons Learned
185 | - [Lesson 1]
186 | - [Lesson 2]
187 | - [Lesson 3]
188 | 
189 | ## Future Considerations
190 | - [Future enhancement 1]
191 | - [Future enhancement 2]
192 | 
193 | ## References
194 | - [Link to reflection document]
195 | - [Link to creative phase documents]
196 | - [Other relevant references]
197 | ```
198 | 
199 | ## 📋 ARCHIVE LOCATION AND NAMING
200 | 
201 | Archive documents should be organized following this pattern:
202 | 
203 | ```mermaid
204 | graph TD
205 |     subgraph "Archive Structure"
206 |         Root["docs/archive/"]
207 |         Tasks["tasks/"]
208 |         Features["features/"]
209 |         Systems["systems/"]
210 |         
211 |         Root --> Tasks
212 |         Root --> Features
213 |         Root --> Systems
214 |         
215 |         Tasks --> Bug["bug-fix-name-YYYYMMDD.md"]
216 |         Tasks --> Enhancement["enhancement-name-YYYYMMDD.md"]
217 |         Features --> Feature["feature-name-YYYYMMDD.md"]
218 |         Systems --> System["system-name-YYYYMMDD.md"]
219 |     end
220 | ```
221 | 
222 | ## 📊 TASKS.MD FINAL UPDATE
223 | 
224 | When archiving is complete, update tasks.md with:
225 | 
226 | ```
227 | ## Status
228 | - [x] Initialization complete
229 | - [x] Planning complete
230 | [For Level 3-4:]
231 | - [x] Creative phases complete
232 | - [x] Implementation complete
233 | - [x] Reflection complete
234 | - [x] Archiving complete
235 | 
236 | ## Archive
237 | - **Date**: [Completion date]
238 | - **Archive Document**: [Link to archive document]
239 | - **Status**: COMPLETED
240 | ```
241 | 
242 | ## 📋 ARCHIVE VERIFICATION CHECKLIST
243 | 
244 | ```
245 | ✓ ARCHIVE VERIFICATION
246 | - Reflection document reviewed? [YES/NO]
247 | - Archive document created with all sections? [YES/NO]
248 | - Archive document placed in correct location? [YES/NO]
249 | - tasks.md marked as completed? [YES/NO]
250 | - progress.md updated with archive reference? [YES/NO]
251 | - activeContext.md updated for next task? [YES/NO]
252 | - Creative phase documents archived (Level 3-4)? [YES/NO/NA]
253 | 
254 | → If all YES: Archiving complete - Memory Bank reset for next task
255 | → If any NO: Complete missing archive elements
256 | ```
257 | 
258 | ## 🔄 TASK COMPLETION NOTIFICATION
259 | 
260 | When archiving is complete, notify user with:
261 | 
262 | ```
263 | ## TASK ARCHIVED
264 | 
265 | ✅ Archive document created in docs/archive/
266 | ✅ All task documentation preserved
267 | ✅ Memory Bank updated with references
268 | ✅ Task marked as COMPLETED
269 | 
270 | → Memory Bank is ready for the next task
271 | → To start a new task, use VAN MODE
272 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/creative-mode-map.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for CREATIVE mode (Design Decisions)
  3 | globs: "**/creative*/**", "**/design*/**", "**/decision*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # CREATIVE MODE: DESIGN PROCESS MAP
  8 | 
  9 | > **TL;DR:** This visual map guides the CREATIVE mode process, focusing on structured design decision-making for components that require deeper exploration before implementation.
 10 | 
 11 | ## 🧭 CREATIVE MODE PROCESS FLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["START CREATIVE MODE"] --> ReadTasks["Read tasks.md<br>For Creative Requirements"]
 16 |     
 17 |     %% Initial Assessment
 18 |     ReadTasks --> VerifyPlan{"Plan Complete<br>& Creative Phases<br>Identified?"}
 19 |     VerifyPlan -->|"No"| ReturnPlan["Return to<br>PLAN Mode"]
 20 |     VerifyPlan -->|"Yes"| IdentifyPhases["Identify Creative<br>Phases Required"]
 21 |     
 22 |     %% Creative Phase Selection
 23 |     IdentifyPhases --> SelectPhase["Select Next<br>Creative Phase"]
 24 |     SelectPhase --> PhaseType{"Creative<br>Phase Type?"}
 25 |     
 26 |     %% Creative Phase Types
 27 |     PhaseType -->|"UI/UX<br>Design"| UIPhase["UI/UX CREATIVE PHASE<br>Core/creative-phase-uiux.md"]
 28 |     PhaseType -->|"Architecture<br>Design"| ArchPhase["ARCHITECTURE CREATIVE PHASE<br>Core/creative-phase-architecture.md"]
 29 |     PhaseType -->|"Data Model<br>Design"| DataPhase["DATA MODEL CREATIVE PHASE<br>Core/creative-phase-data.md"]
 30 |     PhaseType -->|"Algorithm<br>Design"| AlgoPhase["ALGORITHM CREATIVE PHASE<br>Core/creative-phase-algorithm.md"]
 31 |     
 32 |     %% UI/UX Creative Phase
 33 |     UIPhase --> UI_Problem["Define UI/UX<br>Problem"]
 34 |     UI_Problem --> UI_Research["Research UI<br>Patterns"]
 35 |     UI_Research --> UI_Options["Explore UI<br>Options"]
 36 |     UI_Options --> UI_Evaluate["Evaluate User<br>Experience"]
 37 |     UI_Evaluate --> UI_Decision["Make Design<br>Decision"]
 38 |     UI_Decision --> UI_Document["Document UI<br>Design"]
 39 |     
 40 |     %% Architecture Creative Phase
 41 |     ArchPhase --> Arch_Problem["Define Architecture<br>Challenge"]
 42 |     Arch_Problem --> Arch_Options["Explore Architecture<br>Options"]
 43 |     Arch_Options --> Arch_Analyze["Analyze Tradeoffs"]
 44 |     Arch_Analyze --> Arch_Decision["Make Architecture<br>Decision"]
 45 |     Arch_Decision --> Arch_Document["Document<br>Architecture"]
 46 |     Arch_Document --> Arch_Diagram["Create Architecture<br>Diagram"]
 47 |     
 48 |     %% Data Model Creative Phase
 49 |     DataPhase --> Data_Requirements["Define Data<br>Requirements"]
 50 |     Data_Requirements --> Data_Structure["Design Data<br>Structure"]
 51 |     Data_Structure --> Data_Relations["Define<br>Relationships"]
 52 |     Data_Relations --> Data_Validation["Design<br>Validation"]
 53 |     Data_Validation --> Data_Document["Document<br>Data Model"]
 54 |     
 55 |     %% Algorithm Creative Phase
 56 |     AlgoPhase --> Algo_Problem["Define Algorithm<br>Problem"]
 57 |     Algo_Problem --> Algo_Options["Explore Algorithm<br>Approaches"]
 58 |     Algo_Options --> Algo_Evaluate["Evaluate Time/Space<br>Complexity"]
 59 |     Algo_Evaluate --> Algo_Decision["Make Algorithm<br>Decision"]
 60 |     Algo_Decision --> Algo_Document["Document<br>Algorithm"]
 61 |     
 62 |     %% Documentation & Completion
 63 |     UI_Document & Arch_Diagram & Data_Document & Algo_Document --> CreateDoc["Create Creative<br>Phase Document"]
 64 |     CreateDoc --> UpdateTasks["Update tasks.md<br>with Decision"]
 65 |     UpdateTasks --> MorePhases{"More Creative<br>Phases?"}
 66 |     MorePhases -->|"Yes"| SelectPhase
 67 |     MorePhases -->|"No"| VerifyComplete["Verify All<br>Phases Complete"]
 68 |     VerifyComplete --> NotifyComplete["Signal Creative<br>Phases Complete"]
 69 | ```
 70 | 
 71 | ## 📋 CREATIVE PHASE DOCUMENT FORMAT
 72 | 
 73 | Each creative phase should produce a document with this structure:
 74 | 
 75 | ```mermaid
 76 | graph TD
 77 |     subgraph "Creative Phase Document"
 78 |         Header["🎨 CREATIVE PHASE: [TYPE]"]
 79 |         Problem["PROBLEM STATEMENT<br>Clear definition of the problem"]
 80 |         Options["OPTIONS ANALYSIS<br>Multiple approaches considered"]
 81 |         Pros["PROS & CONS<br>Tradeoffs for each option"]
 82 |         Decision["DECISION<br>Selected approach + rationale"]
 83 |         Impl["IMPLEMENTATION PLAN<br>Steps to implement the decision"]
 84 |         Diagram["VISUALIZATION<br>Diagrams of the solution"]
 85 |     end
 86 |     
 87 |     Header --> Problem --> Options --> Pros --> Decision --> Impl --> Diagram
 88 | ```
 89 | 
 90 | ## 🔍 CREATIVE TYPES AND APPROACHES
 91 | 
 92 | ```mermaid
 93 | graph TD
 94 |     subgraph "UI/UX Design"
 95 |         UI1["User Flow<br>Analysis"]
 96 |         UI2["Component<br>Hierarchy"]
 97 |         UI3["Interaction<br>Patterns"]
 98 |         UI4["Visual Design<br>Principles"]
 99 |     end
100 |     
101 |     subgraph "Architecture Design"
102 |         A1["Component<br>Structure"]
103 |         A2["Data Flow<br>Patterns"]
104 |         A3["Interface<br>Design"]
105 |         A4["System<br>Integration"]
106 |     end
107 |     
108 |     subgraph "Data Model Design"
109 |         D1["Entity<br>Relationships"]
110 |         D2["Schema<br>Design"]
111 |         D3["Validation<br>Rules"]
112 |         D4["Query<br>Optimization"]
113 |     end
114 |     
115 |     subgraph "Algorithm Design"
116 |         AL1["Complexity<br>Analysis"]
117 |         AL2["Efficiency<br>Optimization"]
118 |         AL3["Edge Case<br>Handling"]
119 |         AL4["Scaling<br>Considerations"]
120 |     end
121 | ```
122 | 
123 | ## 📊 REQUIRED FILE STATE VERIFICATION
124 | 
125 | Before creative phase work can begin, verify file state:
126 | 
127 | ```mermaid
128 | graph TD
129 |     Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>planning complete?"}
130 |     
131 |     CheckTasks -->|"No"| ErrorPlan["ERROR:<br>Return to PLAN Mode"]
132 |     CheckTasks -->|"Yes"| CheckCreative{"Creative phases<br>identified?"}
133 |     
134 |     CheckCreative -->|"No"| ErrorCreative["ERROR:<br>Return to PLAN Mode"]
135 |     CheckCreative -->|"Yes"| ReadyCreative["Ready for<br>Creative Phase"]
136 | ```
137 | 
138 | ## 📋 OPTIONS ANALYSIS TEMPLATE
139 | 
140 | For each creative phase, analyze multiple options:
141 | 
142 | ```
143 | ## OPTIONS ANALYSIS
144 | 
145 | ### Option 1: [Name]
146 | **Description**: [Brief description]
147 | **Pros**:
148 | - [Pro 1]
149 | - [Pro 2]
150 | **Cons**:
151 | - [Con 1]
152 | - [Con 2]
153 | **Complexity**: [Low/Medium/High]
154 | **Implementation Time**: [Estimate]
155 | 
156 | ### Option 2: [Name]
157 | **Description**: [Brief description]
158 | **Pros**:
159 | - [Pro 1]
160 | - [Pro 2]
161 | **Cons**:
162 | - [Con 1]
163 | - [Con 2]
164 | **Complexity**: [Low/Medium/High]
165 | **Implementation Time**: [Estimate]
166 | 
167 | ### Option 3: [Name]
168 | **Description**: [Brief description]
169 | **Pros**:
170 | - [Pro 1]
171 | - [Pro 2]
172 | **Cons**:
173 | - [Con 1]
174 | - [Con 2]
175 | **Complexity**: [Low/Medium/High]
176 | **Implementation Time**: [Estimate]
177 | ```
178 | 
179 | ## 🎨 CREATIVE PHASE MARKERS
180 | 
181 | Use these visual markers for creative phases:
182 | 
183 | ```
184 | 🎨🎨🎨 ENTERING CREATIVE PHASE: [TYPE] 🎨🎨🎨
185 | 
186 | [Creative phase content]
187 | 
188 | 🎨 CREATIVE CHECKPOINT: [Milestone]
189 | 
190 | [Additional content]
191 | 
192 | 🎨🎨🎨 EXITING CREATIVE PHASE - DECISION MADE 🎨🎨🎨
193 | ```
194 | 
195 | ## 📊 CREATIVE PHASE VERIFICATION CHECKLIST
196 | 
197 | ```
198 | ✓ CREATIVE PHASE VERIFICATION
199 | - Problem clearly defined? [YES/NO]
200 | - Multiple options considered (3+)? [YES/NO]
201 | - Pros/cons documented for each option? [YES/NO]
202 | - Decision made with clear rationale? [YES/NO]
203 | - Implementation plan included? [YES/NO]
204 | - Visualization/diagrams created? [YES/NO]
205 | - tasks.md updated with decision? [YES/NO]
206 | 
207 | → If all YES: Creative phase complete
208 | → If any NO: Complete missing elements
209 | ```
210 | 
211 | ## 🔄 MODE TRANSITION NOTIFICATION
212 | 
213 | When all creative phases are complete, notify user with:
214 | 
215 | ```
216 | ## CREATIVE PHASES COMPLETE
217 | 
218 | ✅ All required design decisions made
219 | ✅ Creative phase documents created
220 | ✅ tasks.md updated with decisions
221 | ✅ Implementation plan updated
222 | 
223 | → NEXT RECOMMENDED MODE: IMPLEMENT MODE
224 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/plan-mode-map.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for PLAN mode (Code Implementation)
  3 | globs: plan-mode-map.mdc
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # PLAN MODE: TASK PLANNING PROCESS MAP
  8 | 
  9 | > **TL;DR:** This visual map guides the PLAN mode process, focusing on creating detailed implementation plans based on the complexity level determined during initialization, with mandatory technology validation before implementation.
 10 | 
 11 | ## 🧭 PLAN MODE PROCESS FLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["START PLANNING"] --> ReadTasks["Read tasks.md<br>Core/task-tracking.md"]
 16 |     
 17 |     %% Complexity Level Determination
 18 |     ReadTasks --> CheckLevel{"Determine<br>Complexity Level"}
 19 |     CheckLevel -->|"Level 2"| Level2["LEVEL 2 PLANNING<br>Level2/enhancement-planning.md"]
 20 |     CheckLevel -->|"Level 3"| Level3["LEVEL 3 PLANNING<br>Level3/feature-planning.md"]
 21 |     CheckLevel -->|"Level 4"| Level4["LEVEL 4 PLANNING<br>Level4/system-planning.md"]
 22 |     
 23 |     %% Level 2 Planning
 24 |     Level2 --> L2Review["Review Code<br>Structure"]
 25 |     L2Review --> L2Document["Document<br>Planned Changes"]
 26 |     L2Document --> L2Challenges["Identify<br>Challenges"]
 27 |     L2Challenges --> L2Checklist["Create Task<br>Checklist"]
 28 |     L2Checklist --> L2Update["Update tasks.md<br>with Plan"]
 29 |     
 30 |     %% Level 3 Planning
 31 |     Level3 --> L3Review["Review Codebase<br>Structure"]
 32 |     L3Review --> L3Requirements["Document Detailed<br>Requirements"]
 33 |     L3Requirements --> L3Components["Identify Affected<br>Components"]
 34 |     L3Components --> L3Plan["Create Comprehensive<br>Implementation Plan"]
 35 |     L3Plan --> L3Challenges["Document Challenges<br>& Solutions"]
 36 |     L3Challenges --> L3Update["Update tasks.md<br>with Plan"]
 37 |     
 38 |     %% Level 4 Planning
 39 |     Level4 --> L4Analysis["Codebase Structure<br>Analysis"]
 40 |     L4Analysis --> L4Requirements["Document Comprehensive<br>Requirements"]
 41 |     L4Requirements --> L4Diagrams["Create Architectural<br>Diagrams"]
 42 |     L4Diagrams --> L4Subsystems["Identify Affected<br>Subsystems"]
 43 |     L4Subsystems --> L4Dependencies["Document Dependencies<br>& Integration Points"]
 44 |     L4Dependencies --> L4Plan["Create Phased<br>Implementation Plan"]
 45 |     L4Plan --> L4Update["Update tasks.md<br>with Plan"]
 46 |     
 47 |     %% **NEW: MCP Technology Research Step**
 48 |     L2Update & L3Update & L4Update --> L_MCP_Research["**TECHNOLOGY RESEARCH (MCP)**<br>Use MCP to investigate new libraries/frameworks"]
 49 |     L_MCP_Research --> L_MCP_Workflow["**MCP Workflow**:<br>1. `read_wiki_structure` for overview<br>2. `ask_question` for architecture/use-cases<br>3. `read_wiki_contents` for tutorials<br>4. Update techContext.md with findings"]
 50 |     
 51 |     %% Technology Validation Gate
 52 |     L_MCP_Workflow --> TechGate["⛔ TECHNOLOGY<br>VALIDATION GATE"]
 53 |     TechGate --> TechSelection["Document Technology<br>Stack Selection"]
 54 |     TechSelection --> TechHelloWorld["Create Hello World<br>Proof of Concept"]
 55 |     TechHelloWorld --> TechDependencies["Verify Required<br>Dependencies"]
 56 |     TechDependencies --> TechConfig["Validate Build<br>Configuration"]
 57 |     TechConfig --> TechBuild["Complete Test<br>Build"]
 58 |     TechBuild --> TechVerify["⛔ TECHNOLOGY<br>CHECKPOINT"]
 59 |     
 60 |     %% Verification & Completion
 61 |     L3Plan --> L3Flag["Flag Components<br>Requiring Creative"]
 62 |     L4Plan --> L4Flag["Flag Components<br>Requiring Creative"]
 63 | 
 64 |     TechVerify --> L2Verify["Verify Plan<br>Completeness (L2)"]
 65 |     L3Flag --> L3Verify["Verify Plan<br>Completeness (L3)"]
 66 |     L4Flag --> L4Verify["Verify Plan<br>Completeness (L4)"]
 67 |     
 68 |     L2Verify & L3Verify & L4Verify --> CheckCreative{"Creative<br>Phases<br>Required?"}
 69 |     
 70 |     %% Mode Transition
 71 |     CheckCreative -->|"Yes"| RecCreative["NEXT MODE:<br>CREATIVE MODE"]
 72 |     CheckCreative -->|"No"| RecImplement["NEXT MODE:<br>IMPLEMENT MODE"]
 73 | ```
 74 | 
 75 | ## 📋 LEVEL-SPECIFIC PLANNING APPROACHES
 76 | 
 77 | ```mermaid
 78 | graph TD
 79 |     subgraph "Level 2: Enhancement"
 80 |         L2A["Basic Requirements<br>Analysis"]
 81 |         L2B["Simple Component<br>Identification"]
 82 |         L2C["Linear Implementation<br>Plan"]
 83 |         L2D["Basic Checklist<br>Creation"]
 84 |     end
 85 |     
 86 |     subgraph "Level 3: Feature"
 87 |         L3A["Detailed Requirements<br>Analysis"]
 88 |         L3B["Component Mapping<br>with Dependencies"]
 89 |         L3C["Multi-Phase<br>Implementation Plan"]
 90 |         L3D["Comprehensive<br>Checklist"]
 91 |         L3E["Creative Phase<br>Identification"]
 92 |     end
 93 |     
 94 |     subgraph "Level 4: System"
 95 |         L4A["Architectural<br>Requirements Analysis"]
 96 |         L4B["System Component<br>Mapping"]
 97 |         L4C["Subsystem<br>Integration Plan"]
 98 |         L4D["Phased Implementation<br>Strategy"]
 99 |         L4E["Risk Assessment<br>& Mitigation"]
100 |         L4F["Multiple Creative<br>Phase Requirements"]
101 |     end
102 |     
103 |     L2A --> L2B --> L2C --> L2D
104 |     L3A --> L3B --> L3C --> L3D --> L3E
105 |     L4A --> L4B --> L4C --> L4D --> L4E --> L4F
106 | ```
107 | 
108 | ## 🔧 TECHNOLOGY VALIDATION WORKFLOW
109 | 
110 | ```mermaid
111 | graph TD
112 |     Start["Technology<br>Validation Start"] --> Select["Technology<br>Stack Selection"]
113 |     Select --> Document["Document Chosen<br>Technologies"]
114 |     Document --> POC["Create Minimal<br>Proof of Concept"]
115 |     POC --> Build["Verify Build<br>Process Works"]
116 |     Build --> Dependencies["Validate All<br>Dependencies"]
117 |     Dependencies --> Config["Confirm Configuration<br>Files Are Correct"]
118 |     Config --> Test["Complete Test<br>Build/Run"]
119 |     Test --> Success{"All Checks<br>Pass?"}
120 |     
121 |     Success -->|"Yes"| Ready["Ready for<br>Implementation"]
122 |     Success -->|"No"| Fix["Fix Technology<br>Issues"]
123 |     Fix --> Document
124 | ```
125 | 
126 | ## 📊 REQUIRED FILE STATE VERIFICATION
127 | 
128 | Before planning can begin, verify the file state:
129 | 
130 | ```mermaid
131 | graph TD
132 |     Start["File State<br>Verification"] --> CheckTasks{"tasks.md<br>initialized?"}
133 |     
134 |     CheckTasks -->|"No"| ErrorTasks["ERROR:<br>Return to VAN Mode"]
135 |     CheckTasks -->|"Yes"| CheckActive{"activeContext.md<br>exists?"}
136 |     
137 |     CheckActive -->|"No"| ErrorActive["ERROR:<br>Return to VAN Mode"]
138 |     CheckActive -->|"Yes"| ReadyPlan["Ready for<br>Planning"]
139 | ```
140 | 
141 | ## 📝 TASKS.MD UPDATE FORMAT
142 | 
143 | During planning, update tasks.md with this structure:
144 | 
145 | ```
146 | # Task: [Task name]
147 | 
148 | ## Description
149 | [Detailed description]
150 | 
151 | ## Complexity
152 | Level: [2/3/4]
153 | Type: [Enhancement/Feature/Complex System]
154 | 
155 | ## Technology Stack
156 | - Framework: [Selected framework]
157 | - Build Tool: [Selected build tool]
158 | - Language: [Selected language]
159 | - Storage: [Selected storage mechanism]
160 | 
161 | ## Technology Validation Checkpoints
162 | - [ ] Project initialization command verified
163 | - [ ] Required dependencies identified and installed
164 | - [ ] Build configuration validated
165 | - [ ] Hello world verification completed
166 | - [ ] Test build passes successfully
167 | 
168 | ## Status
169 | - [x] Initialization complete
170 | - [x] Planning complete
171 | - [ ] Technology validation complete
172 | - [ ] [Implementation steps]
173 | 
174 | ## Implementation Plan
175 | 1. [Step 1]
176 |    - [Subtask 1.1]
177 |    - [Subtask 1.2]
178 | 2. [Step 2]
179 |    - [Subtask 2.1]
180 |    - [Subtask 2.2]
181 | 
182 | ## Creative Phases Required
183 | - [ ] [Component 1] Design
184 | - [ ] [Component 2] Architecture
185 | - [ ] [Component 3] Data Model
186 | 
187 | ## Dependencies
188 | - [Dependency 1]
189 | - [Dependency 2]
190 | 
191 | ## Challenges & Mitigations
192 | - [Challenge 1]: [Mitigation strategy]
193 | - [Challenge 2]: [Mitigation strategy]
194 | ```
195 | 
196 | ## 📋 CREATIVE PHASE IDENTIFICATION
197 | 
198 | For Level 3-4 tasks, identify components requiring creative phases:
199 | 
200 | ```mermaid
201 | graph TD
202 |     Start["Creative Phase<br>Identification"] --> CheckComp{"Component<br>Analysis"}
203 |     
204 |     CheckComp --> UI["UI/UX<br>Components"]
205 |     CheckComp --> Data["Data Model<br>Components"]
206 |     CheckComp --> Arch["Architecture<br>Components"]
207 |     CheckComp --> Algo["Algorithm<br>Components"]
208 |     
209 |     UI & Data & Arch & Algo --> Decision{"Design Decisions<br>Required?"}
210 |     
211 |     Decision -->|"Yes"| Flag["Flag for<br>Creative Phase"]
212 |     Decision -->|"No"| Skip["Standard<br>Implementation"]
213 |     
214 |     Flag --> Document["Document in<br>tasks.md"]
215 | ```
216 | 
217 | ## 📊 TECHNOLOGY VALIDATION CHECKLIST
218 | 
219 | ```
220 | ✓ TECHNOLOGY VALIDATION CHECKLIST
221 | - Technology stack clearly defined? [YES/NO]
222 | - Project initialization command documented? [YES/NO]
223 | - Required dependencies identified? [YES/NO]
224 | - Minimal proof of concept created? [YES/NO]
225 | - Hello world build/run successful? [YES/NO]
226 | - Configuration files validated? [YES/NO]
227 | - Test build completes successfully? [YES/NO]
228 | 
229 | → If all YES: Technology validation complete - ready for next phase
230 | → If any NO: Resolve technology issues before proceeding
231 | ```
232 | 
233 | ## 📊 PLAN VERIFICATION CHECKLIST
234 | 
235 | ```
236 | ✓ PLAN VERIFICATION CHECKLIST
237 | - Requirements clearly documented? [YES/NO]
238 | - Technology stack validated? [YES/NO]
239 | - Affected components identified? [YES/NO]
240 | - Implementation steps detailed? [YES/NO]
241 | - Dependencies documented? [YES/NO]
242 | - Challenges & mitigations addressed? [YES/NO]
243 | - Creative phases identified (Level 3-4)? [YES/NO/NA]
244 | - tasks.md updated with plan? [YES/NO]
245 | 
246 | → If all YES: Planning complete - ready for next mode
247 | → If any NO: Complete missing plan elements
248 | ```
249 | 
250 | ## 🔄 MODE TRANSITION NOTIFICATION
251 | 
252 | When planning is complete, notify user with:
253 | 
254 | ```
255 | ## PLANNING COMPLETE
256 | 
257 | ✅ Implementation plan created
258 | ✅ Technology stack validated
259 | ✅ tasks.md updated with plan
260 | ✅ Challenges and mitigations documented
261 | [✅ Creative phases identified (for Level 3-4)]
262 | 
263 | → NEXT RECOMMENDED MODE: [CREATIVE/IMPLEMENT] MODE 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/reflect-mode-map.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for REFLECT mode (Task Reflection)
  3 | globs: "**/reflect*/**", "**/review*/**", "**/retrospect*/**"
  4 | alwaysApply: false
  5 | ---
  6 | 
  7 | # REFLECT MODE: TASK REVIEW PROCESS MAP
  8 | 
  9 | > **TL;DR:** This visual map guides the REFLECT mode process, focusing on structured review of the implementation, documenting lessons learned, and preparing insights for future reference.
 10 | 
 11 | ## 🧭 REFLECT MODE PROCESS FLOW
 12 | 
 13 | ```mermaid
 14 | graph TD
 15 |     Start["START REFLECT MODE"] --> ReadTasks["Read tasks.md<br>and progress.md"]
 16 |     
 17 |     %% Initial Assessment
 18 |     ReadTasks --> VerifyImplement{"Implementation<br>Complete?"}
 19 |     VerifyImplement -->|"No"| ReturnImplement["Return to<br>IMPLEMENT Mode"]
 20 |     VerifyImplement -->|"Yes"| AssessLevel{"Determine<br>Complexity Level"}
 21 |     
 22 |     %% Level-Based Reflection
 23 |     AssessLevel -->|"Level 1"| L1Reflect["LEVEL 1 REFLECTION<br>Level1/reflection-basic.md"]
 24 |     AssessLevel -->|"Level 2"| L2Reflect["LEVEL 2 REFLECTION<br>Level2/reflection-standard.md"]
 25 |     AssessLevel -->|"Level 3"| L3Reflect["LEVEL 3 REFLECTION<br>Level3/reflection-comprehensive.md"]
 26 |     AssessLevel -->|"Level 4"| L4Reflect["LEVEL 4 REFLECTION<br>Level4/reflection-advanced.md"]
 27 |     
 28 |     %% Level 1 Reflection (Quick)
 29 |     L1Reflect --> L1Review["Review<br>Bug Fix"]
 30 |     L1Review --> L1Document["Document<br>Solution"]
 31 |     L1Document --> L1Update["Update<br>tasks.md"]
 32 |     
 33 |     %% Level 2 Reflection (Standard)
 34 |     L2Reflect --> L2Review["Review<br>Enhancement"]
 35 |     L2Review --> L2WWW["Document<br>What Went Well"]
 36 |     L2WWW --> L2Challenges["Document<br>Challenges"]
 37 |     L2Challenges --> L2Lessons["Document<br>Lessons Learned"]
 38 |     L2Lessons --> L2Update["Update<br>tasks.md"]
 39 |     
 40 |     %% Level 3-4 Reflection (Comprehensive)
 41 |     L3Reflect & L4Reflect --> L34Review["Review Implementation<br>& Creative Phases"]
 42 |     L34Review --> L34Plan["Compare Against<br>Original Plan"]
 43 |     L34Plan --> L34WWW["Document<br>What Went Well"]
 44 |     L34WWW --> L34Challenges["Document<br>Challenges"]
 45 |     L34Challenges --> L34Lessons["Document<br>Lessons Learned"]
 46 |     L34Lessons --> L34ImproveProcess["Document Process<br>Improvements"]
 47 |     L34ImproveProcess --> L34Update["Update<br>tasks.md"]
 48 |     
 49 |     %% Completion & Transition
 50 |     L1Update & L2Update & L34Update --> CreateReflection["Create<br>reflection.md"]
 51 |     CreateReflection --> UpdateSystem["Update System<br>Documentation"]
 52 |     UpdateSystem --> Transition["NEXT MODE:<br>ARCHIVE MODE"]
 53 | ```
 54 | 
 55 | ## 📋 REFLECTION STRUCTURE
 56 | 
 57 | The reflection should follow this structured format:
 58 | 
 59 | ```mermaid
 60 | graph TD
 61 |     subgraph "Reflection Document Structure"
 62 |         Header["# TASK REFLECTION: [Task Name]"]
 63 |         Summary["## SUMMARY<br>Brief summary of completed task"]
 64 |         WWW["## WHAT WENT WELL<br>Successful aspects of implementation"]
 65 |         Challenges["## CHALLENGES<br>Difficulties encountered during implementation"]
 66 |         Lessons["## LESSONS LEARNED<br>Key insights gained from the experience"]
 67 |         ProcessImp["## PROCESS IMPROVEMENTS<br>How to improve for future tasks"]
 68 |         TechImp["## TECHNICAL IMPROVEMENTS<br>Better approaches for similar tasks"]
 69 |         NextSteps["## NEXT STEPS<br>Follow-up actions or future work"]
 70 |     end
 71 |     
 72 |     Header --> Summary --> WWW --> Challenges --> Lessons --> ProcessImp --> TechImp --> NextSteps
 73 | ```
 74 | 
 75 | ## 📊 REQUIRED FILE STATE VERIFICATION
 76 | 
 77 | Before reflection can begin, verify file state:
 78 | 
 79 | ```mermaid
 80 | graph TD
 81 |     Start["File State<br>Verification"] --> CheckTasks{"tasks.md has<br>implementation<br>complete?"}
 82 |     
 83 |     CheckTasks -->|"No"| ErrorImplement["ERROR:<br>Return to IMPLEMENT Mode"]
 84 |     CheckTasks -->|"Yes"| CheckProgress{"progress.md<br>has implementation<br>details?"}
 85 |     
 86 |     CheckProgress -->|"No"| ErrorProgress["ERROR:<br>Update progress.md first"]
 87 |     CheckProgress -->|"Yes"| ReadyReflect["Ready for<br>Reflection"]
 88 | ```
 89 | 
 90 | ## 🔍 IMPLEMENTATION REVIEW APPROACH
 91 | 
 92 | ```mermaid
 93 | graph TD
 94 |     subgraph "Implementation Review"
 95 |         Original["Review Original<br>Requirements"]
 96 |         Plan["Compare Against<br>Implementation Plan"]
 97 |         Actual["Assess Actual<br>Implementation"]
 98 |         Creative["Review Creative<br>Phase Decisions"]
 99 |         Changes["Identify Deviations<br>from Plan"]
100 |         Results["Evaluate<br>Results"]
101 |     end
102 |     
103 |     Original --> Plan --> Actual
104 |     Plan --> Creative --> Changes
105 |     Actual --> Results
106 |     Changes --> Results
107 | ```
108 | 
109 | ## 📝 REFLECTION DOCUMENT TEMPLATES
110 | 
111 | ### Level 1 (Basic) Reflection
112 | ```
113 | # Bug Fix Reflection: [Bug Name]
114 | 
115 | ## Summary
116 | [Brief description of the bug and solution]
117 | 
118 | ## Implementation
119 | [Description of the fix implemented]
120 | 
121 | ## Testing
122 | [Description of testing performed]
123 | 
124 | ## Additional Notes
125 | [Any other relevant information]
126 | ```
127 | 
128 | ### Levels 2-4 (Comprehensive) Reflection
129 | ```
130 | # Task Reflection: [Task Name]
131 | 
132 | ## Summary
133 | [Brief summary of the task and what was achieved]
134 | 
135 | ## What Went Well
136 | - [Success point 1]
137 | - [Success point 2]
138 | - [Success point 3]
139 | 
140 | ## Challenges
141 | - [Challenge 1]: [How it was addressed]
142 | - [Challenge 2]: [How it was addressed]
143 | - [Challenge 3]: [How it was addressed]
144 | 
145 | ## Lessons Learned
146 | - [Lesson 1]
147 | - [Lesson 2]
148 | - [Lesson 3]
149 | 
150 | ## Process Improvements
151 | - [Process improvement 1]
152 | - [Process improvement 2]
153 | 
154 | ## Technical Improvements
155 | - [Technical improvement 1]
156 | - [Technical improvement 2]
157 | 
158 | ## Next Steps
159 | - [Follow-up task 1]
160 | - [Follow-up task 2]
161 | ```
162 | 
163 | ## 📊 REFLECTION QUALITY METRICS
164 | 
165 | ```mermaid
166 | graph TD
167 |     subgraph "Reflection Quality Metrics"
168 |         Specific["Specific<br>Not general or vague"]
169 |         Actionable["Actionable<br>Provides clear direction"]
170 |         Honest["Honest<br>Acknowledges successes and failures"]
171 |         Forward["Forward-Looking<br>Focuses on future improvement"]
172 |         Evidence["Evidence-Based<br>Based on concrete examples"]
173 |     end
174 | ```
175 | 
176 | ## 📋 TASKS.MD UPDATE FORMAT
177 | 
178 | During reflection, update tasks.md with:
179 | 
180 | ```
181 | ## Status
182 | - [x] Initialization complete
183 | - [x] Planning complete
184 | [For Level 3-4:]
185 | - [x] Creative phases complete
186 | - [x] Implementation complete
187 | - [x] Reflection complete
188 | - [ ] Archiving
189 | 
190 | ## Reflection Highlights
191 | - **What Went Well**: [Key successes]
192 | - **Challenges**: [Key challenges]
193 | - **Lessons Learned**: [Key lessons]
194 | - **Next Steps**: [Follow-up actions]
195 | ```
196 | 
197 | ## 📊 REFLECTION VERIFICATION CHECKLIST
198 | 
199 | ```
200 | ✓ REFLECTION VERIFICATION
201 | - Implementation thoroughly reviewed? [YES/NO]
202 | - What Went Well section completed? [YES/NO]
203 | - Challenges section completed? [YES/NO]
204 | - Lessons Learned section completed? [YES/NO]
205 | - Process Improvements identified? [YES/NO]
206 | - Technical Improvements identified? [YES/NO]
207 | - Next Steps documented? [YES/NO]
208 | - reflection.md created? [YES/NO]
209 | - tasks.md updated with reflection status? [YES/NO]
210 | 
211 | → If all YES: Reflection complete - ready for ARCHIVE mode
212 | → If any NO: Complete missing reflection elements
213 | ```
214 | 
215 | ## 🔄 MODE TRANSITION NOTIFICATION
216 | 
217 | When reflection is complete, notify user with:
218 | 
219 | ```
220 | ## REFLECTION COMPLETE
221 | 
222 | ✅ Implementation thoroughly reviewed
223 | ✅ Reflection document created
224 | ✅ Lessons learned documented
225 | ✅ Process improvements identified
226 | ✅ tasks.md updated with reflection status
227 | 
228 | → NEXT RECOMMENDED MODE: ARCHIVE MODE
229 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-complexity-determination.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for VAN mode complexity determination
  3 | globs: van-complexity-determination.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # VAN MODE: COMPLEXITY DETERMINATION
  7 | 
  8 | > **TL;DR:** This component determines the appropriate complexity level (1-4) for the current task and directs the workflow accordingly.
  9 | 
 10 | ## 🔍 COMPLEXITY DECISION TREE
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["New Task"] --> Q1{"Bug fix or<br>error correction?"}
 15 |     Q1 -->|Yes| Q1a{"Affects single<br>component?"}
 16 |     Q1a -->|Yes| L1["Level 1:<br>Quick Bug Fix"]
 17 |     Q1a -->|No| Q1b{"Affects multiple<br>components?"}
 18 |     Q1b -->|Yes| L2["Level 2:<br>Simple Enhancement"]
 19 |     Q1b -->|No| Q1c{"Affects system<br>architecture?"}
 20 |     Q1c -->|Yes| L3["Level 3:<br>Intermediate Feature"]
 21 |     Q1c -->|No| L2
 22 |     
 23 |     Q1 -->|No| Q2{"Adding small<br>feature or<br>enhancement?"}
 24 |     Q2 -->|Yes| Q2a{"Self-contained<br>change?"}
 25 |     Q2a -->|Yes| L2
 26 |     Q2a -->|No| Q2b{"Affects multiple<br>components?"}
 27 |     Q2b -->|Yes| L3
 28 |     Q2b -->|No| L2
 29 |     
 30 |     Q2 -->|No| Q3{"Complete feature<br>requiring multiple<br>components?"}
 31 |     Q3 -->|Yes| Q3a{"Architectural<br>implications?"}
 32 |     Q3a -->|Yes| L4["Level 4:<br>Complex System"]
 33 |     Q3a -->|No| L3
 34 |     
 35 |     Q3 -->|No| Q4{"System-wide or<br>architectural<br>change?"}
 36 |     Q4 -->|Yes| L4
 37 |     Q4 -->|No| L3
 38 | ```
 39 | 
 40 | ## 📋 LEVEL INDICATORS
 41 | 
 42 | ### Level 1: Quick Bug Fix
 43 | - **Keywords**: fix, bug, error, crash, issue
 44 | - **Scope**: Single component
 45 | - **Time**: Minutes to hours
 46 | - **Risk**: Low, isolated
 47 | - **Example**: Button not working, styling issue
 48 | 
 49 | ### Level 2: Simple Enhancement
 50 | - **Keywords**: add, improve, update, enhance
 51 | - **Scope**: Single component/subsystem
 52 | - **Time**: Hours to 1-2 days
 53 | - **Risk**: Moderate, contained
 54 | - **Example**: Add form field, improve validation
 55 | 
 56 | ### Level 3: Intermediate Feature
 57 | - **Keywords**: implement, create, develop
 58 | - **Scope**: Multiple components
 59 | - **Time**: Days to 1-2 weeks
 60 | - **Risk**: Significant
 61 | - **Example**: User authentication, dashboard
 62 | 
 63 | ### Level 4: Complex System
 64 | - **Keywords**: system, architecture, redesign
 65 | - **Scope**: Multiple subsystems
 66 | - **Time**: Weeks to months
 67 | - **Risk**: High, architectural
 68 | - **Example**: Payment system, microservices
 69 | 
 70 | ## 📋 COMPLEXITY CHECKLIST
 71 | 
 72 | ```
 73 | ✓ COMPLEXITY DETERMINATION
 74 | - Task type identified? [YES/NO]
 75 | - Scope assessed? [YES/NO]
 76 | - Time estimated? [YES/NO]
 77 | - Risk evaluated? [YES/NO]
 78 | - Dependencies mapped? [YES/NO]
 79 | 
 80 | → If all YES: Proceed with level-specific workflow
 81 | → If any NO: Complete assessment
 82 | ```
 83 | 
 84 | ## 🔄 LEVEL TRANSITION TRIGGERS
 85 | 
 86 | ```mermaid
 87 | graph TD
 88 |     Current["Current Level"] --> Higher["Level Up Triggers"]
 89 |     Current --> Lower["Level Down Triggers"]
 90 |     
 91 |     Higher --> H1["Multiple Components"]
 92 |     Higher --> H2["Design Decisions"]
 93 |     Higher --> H3["System Impact"]
 94 |     
 95 |     Lower --> L1["Isolated Change"]
 96 |     Lower --> L2["Simple Fix"]
 97 |     Lower --> L3["No Design Needed"]
 98 | ```
 99 | 
100 | ## 📋 WORKFLOW LOADING
101 | 
102 | Based on determined level:
103 | - Level 1: Continue in VAN mode
104 | - Level 2-4: Transition to PLAN mode
105 | 
106 | **Next Step:** Load appropriate level-specific workflow
107 | 
108 | ## 🚨 MODE TRANSITION TRIGGER (VAN to PLAN)
109 | 
110 | If complexity is determined to be Level 2, 3, or 4:
111 | 
112 | ```
113 | 🚫 LEVEL [2-4] TASK DETECTED
114 | Implementation in VAN mode is BLOCKED
115 | This task REQUIRES PLAN mode
116 | You MUST switch to PLAN mode for proper documentation and planning
117 | Type 'PLAN' to switch to planning mode
118 | ```
119 | 
120 | ## 📋 CHECKPOINT VERIFICATION TEMPLATE (Example)
121 | 
122 | ```
123 | ✓ SECTION CHECKPOINT: COMPLEXITY DETERMINATION
124 | - Task Analyzed? [YES/NO]
125 | - Complexity Level Determined? [YES/NO]
126 | 
127 | → If Level 1: Proceed to VAN Mode Completion.
128 | → If Level 2-4: Trigger PLAN Mode transition.
129 | ```
130 | 
131 | **Next Step (Level 1):** Complete VAN Initialization (e.g., initialize Memory Bank if needed).
132 | **Next Step (Level 2-4):** Exit VAN mode and initiate PLAN mode. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-file-verification.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for VAN mode file verification
  3 | globs: van-file-verification.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # OPTIMIZED FILE VERIFICATION SYSTEM
  7 | 
  8 | 🚨 CRITICAL: MEMORY BANK VERIFICATION REQUIRED 🚨
  9 | Memory Bank structure MUST exist before any file operations
 10 | This check MUST be executed first in all verification processes
 11 | 
 12 | > **TL;DR:** This system provides a structured approach to verify file structure integrity before task implementation, with emphasis on efficient checks and clear status reporting.
 13 | 
 14 | ## 🔍 FILE VERIFICATION WORKFLOW
 15 | 
 16 | ```mermaid
 17 | graph TD
 18 |     %% Critical Memory Bank verification - MUST be first
 19 |     Start["Start File Verification"] --> MemBankCheck{"Memory Bank<br>Exists?"}
 20 |     MemBankCheck -->|"No"| CreateMemBank["CREATE MEMORY BANK<br>[CRITICAL]"]
 21 |     MemBankCheck -->|"Yes"| VerifyMemBankComplete["Verify Memory Bank<br>Structure Complete"]
 22 |     CreateMemBank --> VerifyMemBankComplete
 23 |     
 24 |     VerifyMemBankComplete --> PassCheck{"All Critical<br>Checks Pass?"}
 25 |     PassCheck -->|"No"| AbortAll["⛔ ABORT ALL OPERATIONS<br>Fix Memory Bank First"]
 26 |     PassCheck -->|"Yes"| MainVerification
 27 | 
 28 |     %% Regular verification flow continues here
 29 |     MainVerification["Start Full<br>File Verification"] --> BatchVerify["Batch Verification<br>Using Patterns"]
 30 |     BatchVerify --> BrokenLinks["Check for<br>Broken References"]
 31 |     BrokenLinks --> DirectoryStructure["Verify Directory<br>Structure"]
 32 |     DirectoryStructure --> Status{"All Verifications<br>Successful?"}
 33 |     
 34 |     Status -->|"Yes"| Complete["Verification<br>Complete ✓"]
 35 |     Status -->|"No"| Diagnose["Diagnose<br>Issues"]
 36 |     Diagnose --> Attempt{"Attempt Auto<br>Resolution?"}
 37 |     
 38 |     Attempt -->|"Yes"| AutoFix["Auto-Fix<br>Issues"]
 39 |     Attempt -->|"No"| ReportIssue["Report Issues to<br>User"]
 40 |     
 41 |     AutoFix --> Recheck{"Issues<br>Resolved?"}
 42 |     Recheck -->|"Yes"| ReportSuccess["Report Success<br>to User"]
 43 |     Recheck -->|"No"| ReportIssue
 44 |     
 45 |     ReportSuccess --> Complete
 46 |     ReportIssue --> UserAction["Wait for<br>User Action"]
 47 |     UserAction --> ReVerify["Re-Verify<br>After User Action"]
 48 |     ReVerify --> Status
 49 | ```
 50 | 
 51 | ## 🧩 MEMORY BANK VERIFICATION - CRITICAL COMPONENT
 52 | 
 53 | Memory Bank verification MUST be executed first in any file verification process:
 54 | 
 55 | ```javascript
 56 | function verifyMemoryBank() {
 57 |   // Check if Memory Bank exists
 58 |   const memoryBankExists = checkDirectoryExists("documentation\memory-bank");
 59 |   if (!memoryBankExists) {
 60 |     console.error("⛔ CRITICAL ERROR: Memory Bank does not exist");
 61 |     createMemoryBankStructure();
 62 |     return verifyMemoryBankCreation();
 63 |   }
 64 |   
 65 |   // Check required subdirectories
 66 |   const requiredDirs = [
 67 |     "documentation\memory-bank/active-context",
 68 |     "documentation\memory-bank/system-patterns",
 69 |     "documentation\memory-bank/creative-phase",
 70 |     "documentation\memory-bank/implementation"
 71 |   ];
 72 |   
 73 |   const missingDirs = requiredDirs.filter(dir => !checkDirectoryExists(dir));
 74 |   if (missingDirs.length > 0) {
 75 |     console.error(`⛔ CRITICAL ERROR: Missing Memory Bank directories: ${missingDirs.join(", ")}`);
 76 |     createMissingDirectories(missingDirs);
 77 |     return verifyMemoryBankCreation();
 78 |   }
 79 |   
 80 |   // Check critical files
 81 |   const criticalFiles = [
 82 |     "documentation\memory-bank/active-context/activeContext.md",
 83 |     "documentation\memory-bank/system-patterns/systemPatterns.md"
 84 |   ];
 85 |   
 86 |   const missingFiles = criticalFiles.filter(file => !checkFileExists(file));
 87 |   if (missingFiles.length > 0) {
 88 |     console.error(`⛔ CRITICAL ERROR: Missing critical files: ${missingFiles.join(", ")}`);
 89 |     createMissingFiles(missingFiles);
 90 |     return verifyMemoryBankCreation();
 91 |   }
 92 |   
 93 |   return true; // Memory Bank verification successful
 94 | }
 95 | 
 96 | // MANDATORY: This must be called before any other verification
 97 | const memoryBankVerified = verifyMemoryBank();
 98 | if (!memoryBankVerified) {
 99 |   throw new Error("⛔ MEMORY BANK VERIFICATION FAILED - CANNOT PROCEED");
100 | }
101 | ```
102 | 
103 | ## 📋 MEMORY BANK VERIFICATION CHECKLIST
104 | 
105 | ```
106 | ✓ MEMORY BANK VERIFICATION CHECKLIST
107 | - Memory Bank directory exists? [YES/NO]
108 | - Required subdirectories exist? [YES/NO]
109 | - Critical files exist? [YES/NO]
110 | - File content is valid? [YES/NO]
111 | 
112 | → If ALL YES: Memory Bank verification passed - Continue file verification
113 | → If ANY NO: STOP ALL PROCESSING and FIX MEMORY BANK
114 | ```
115 | 
116 | ## 🔍 BATCH VERIFICATION WORKFLOW
117 | 
118 | ## 📋 OPTIMIZED DIRECTORY CREATION
119 | 
120 | ```mermaid
121 | graph TD
122 |     Start["Directory<br>Creation"] --> DetectOS["Detect Operating<br>System"]
123 |     DetectOS -->|"Windows"| WinCmd["Batch Create<br>Windows Command"]
124 |     DetectOS -->|"Mac/Linux"| UnixCmd["Batch Create<br>Unix Command"]
125 |     WinCmd & UnixCmd --> Verify["Verify<br>Creation Success"]
126 |     Verify --> Complete["Directory Setup<br>Complete"]
127 | ```
128 | 
129 | ### Platform-Specific Commands
130 | 
131 | #### Windows (PowerShell)
132 | ```powershell
133 | # Create all directories in one command
134 | mkdir documentation\memory-bank, docs, docs\archive -ErrorAction SilentlyContinue
135 | 
136 | # Create all required files
137 | $files = @(".cursorrules", "tasks.md", 
138 |            "documentation\memory-bank\projectbrief.md", 
139 |            "documentation\memory-bank\productContext.md",
140 |            "documentation\memory-bank\systemPatterns.md",
141 |            "documentation\memory-bank\techContext.md",
142 |            "documentation\memory-bank\activeContext.md",
143 |            "documentation\memory-bank\progress.md")
144 | 
145 | foreach ($file in $files) {
146 |     if (-not (Test-Path $file)) {
147 |         New-Item -Path $file -ItemType File -Force
148 |     }
149 | }
150 | ```
151 | 
152 | #### Mac/Linux (Bash)
153 | ```bash
154 | # Create all directories in one command
155 | mkdir -p documentation\memory-bank docs/archive
156 | 
157 | # Create all required files
158 | touch .cursorrules tasks.md \
159 |       documentation\memory-bank/projectbrief.md \
160 |       documentation\memory-bank/productContext.md \
161 |       documentation\memory-bank/systemPatterns.md \
162 |       documentation\memory-bank/techContext.md \
163 |       documentation\memory-bank/activeContext.md \
164 |       documentation\memory-bank/progress.md
165 | ```
166 | 
167 | ## 📝 STREAMLINED VERIFICATION PROCESS
168 | 
169 | Instead of checking each component separately, perform batch verification:
170 | 
171 | ```powershell
172 | # Windows - PowerShell
173 | $requiredDirs = @("documentation\memory-bank", "docs", "docs\archive")
174 | $requiredFiles = @(".cursorrules", "tasks.md")
175 | $mbFiles = @("projectbrief.md", "productContext.md", "systemPatterns.md", 
176 |              "techContext.md", "activeContext.md", "progress.md")
177 | 
178 | $missingDirs = $requiredDirs | Where-Object { -not (Test-Path $_) -or -not (Test-Path $_ -PathType Container) }
179 | $missingFiles = $requiredFiles | Where-Object { -not (Test-Path $_) -or (Test-Path $_ -PathType Container) }
180 | $missingMBFiles = $mbFiles | ForEach-Object { "documentation\memory-bank\$_" } | 
181 |                   Where-Object { -not (Test-Path $_) -or (Test-Path $_ -PathType Container) }
182 | 
183 | if ($missingDirs.Count -eq 0 -and $missingFiles.Count -eq 0 -and $missingMBFiles.Count -eq 0) {
184 |     Write-Output "✓ All required components verified"
185 | } else {
186 |     # Create all missing items at once
187 |     if ($missingDirs.Count -gt 0) {
188 |         $missingDirs | ForEach-Object { mkdir $_ -Force }
189 |     }
190 |     if ($missingFiles.Count -gt 0 -or $missingMBFiles.Count -gt 0) {
191 |         $allMissingFiles = $missingFiles + $missingMBFiles
192 |         $allMissingFiles | ForEach-Object { New-Item -Path $_ -ItemType File -Force }
193 |     }
194 | }
195 | ```
196 | 
197 | ## 📝 TEMPLATE INITIALIZATION
198 | 
199 | Optimize template creation with a single script:
200 | 
201 | ```powershell
202 | # Windows - PowerShell
203 | $templates = @{
204 |     "tasks.md" = @"
205 | # Memory Bank: Tasks
206 | 
207 | ## Current Task
208 | [Task not yet defined]
209 | 
210 | ## Status
211 | - [ ] Task definition
212 | - [ ] Implementation plan
213 | - [ ] Execution
214 | - [ ] Documentation
215 | 
216 | ## Requirements
217 | [No requirements defined yet]
218 | "@
219 | 
220 |     "documentation\memory-bank\activeContext.md" = @"
221 | # Memory Bank: Active Context
222 | 
223 | ## Current Focus
224 | [No active focus defined]
225 | 
226 | ## Status
227 | [No status defined]
228 | 
229 | ## Latest Changes
230 | [No changes recorded]
231 | "@
232 | 
233 |     # Add other templates here
234 | }
235 | 
236 | foreach ($file in $templates.Keys) {
237 |     if (Test-Path $file) {
238 |         Set-Content -Path $file -Value $templates[$file]
239 |     }
240 | }
241 | ```
242 | 
243 | ## 🔍 PERFORMANCE OPTIMIZATION BEST PRACTICES
244 | 
245 | 1. **Batch Operations**: Always use batch operations instead of individual commands
246 |    ```
247 |    # GOOD: Create all directories at once
248 |    mkdir documentation\memory-bank docs docs\archive
249 |    
250 |    # BAD: Create directories one at a time
251 |    mkdir documentation\memory-bank
252 |    mkdir docs
253 |    mkdir docs\archive
254 |    ```
255 | 
256 | 2. **Pre-Check Optimization**: Check all requirements first, then create only what's missing
257 |    ```
258 |    # First check what's missing
259 |    $missingItems = ...
260 |    
261 |    # Then create only what's missing
262 |    if ($missingItems) { ... }
263 |    ```
264 | 
265 | 3. **Error Handling**: Include error handling in all commands
266 |    ```
267 |    mkdir documentation\memory-bank, docs, docs\archive -ErrorAction SilentlyContinue
268 |    ```
269 | 
270 | 4. **Platform Adaptation**: Auto-detect platform and use appropriate commands
271 |    ```
272 |    if ($IsWindows) {
273 |        # Windows commands
274 |    } else {
275 |        # Unix commands
276 |    }
277 |    ```
278 | 
279 | 5. **One-Pass Verification**: Verify directory structure in a single pass
280 |    ```
281 |    $requiredPaths = @("documentation\memory-bank", "docs", "docs\archive", ".cursorrules", "tasks.md")
282 |    $missingPaths = $requiredPaths | Where-Object { -not (Test-Path $_) }
283 |    ```
284 | 
285 | ## 📝 VERIFICATION REPORT FORMAT
286 | 
287 | ```
288 | ✅ VERIFICATION COMPLETE
289 | - Created directories: [list]
290 | - Created files: [list]
291 | - All components verified
292 | 
293 | Memory Bank system ready for use.
294 | ``` 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-platform-detection.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Visual process map for VAN mode platform detection
 3 | globs: van-platform-detection.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN MODE: PLATFORM DETECTION
 7 | 
 8 | > **TL;DR:** Detects the OS, determines path separators, and notes command adaptations required.
 9 | 
10 | ## 🌐 PLATFORM DETECTION PROCESS
11 | 
12 | ```mermaid
13 | graph TD
14 |     PD["Platform Detection"] --> CheckOS["Detect Operating System"]
15 |     CheckOS --> Win["Windows"]
16 |     CheckOS --> Mac["macOS"]
17 |     CheckOS --> Lin["Linux"]
18 |     
19 |     Win & Mac & Lin --> Adapt["Adapt Commands<br>for Platform"]
20 |     
21 |     Win --> WinPath["Path: Backslash (\\)"]
22 |     Mac --> MacPath["Path: Forward Slash (/)"]
23 |     Lin --> LinPath["Path: Forward Slash (/)"]
24 |     
25 |     Win --> WinCmd["Command Adaptations:<br>dir, icacls, etc."]
26 |     Mac --> MacCmd["Command Adaptations:<br>ls, chmod, etc."]
27 |     Lin --> LinCmd["Command Adaptations:<br>ls, chmod, etc."]
28 |     
29 |     WinPath & MacPath & LinPath --> PathCP["Path Separator<br>Checkpoint"]
30 |     WinCmd & MacCmd & LinCmd --> CmdCP["Command<br>Checkpoint"]
31 |     
32 |     PathCP & CmdCP --> PlatformComplete["Platform Detection<br>Complete"]
33 | ```
34 | 
35 | ## 📋 CHECKPOINT VERIFICATION TEMPLATE (Example)
36 | 
37 | ```
38 | ✓ SECTION CHECKPOINT: PLATFORM DETECTION
39 | - Operating System Detected? [YES/NO]
40 | - Path Separator Confirmed? [YES/NO]
41 | - Command Adaptations Noted? [YES/NO]
42 | 
43 | → If all YES: Platform Detection Complete.
44 | → If any NO: Resolve before proceeding.
45 | ```
46 | 
47 | **Next Step:** Load and process `van-file-verification.mdc`. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-checks/build-test.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Process map for VAN QA minimal build test
  3 | globs: van-qa-checks/build-test.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # VAN QA: MINIMAL BUILD TEST
  7 | 
  8 | > **TL;DR:** This component performs a minimal build test to ensure core build functionality works properly.
  9 | 
 10 | ## 4️⃣ MINIMAL BUILD TEST PROCESS
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["Minimal Build Test"] --> CreateTest["Create Minimal<br>Test Project"]
 15 |     CreateTest --> BuildTest["Attempt<br>Build"]
 16 |     BuildTest --> BuildStatus{"Build<br>Successful?"}
 17 |     
 18 |     BuildStatus -->|"Yes"| RunTest["Run Basic<br>Functionality Test"]
 19 |     BuildStatus -->|"No"| FixBuild["Fix Build<br>Issues"]
 20 |     FixBuild --> RetryBuild["Retry Build"]
 21 |     RetryBuild --> BuildStatus
 22 |     
 23 |     RunTest --> TestStatus{"Test<br>Passed?"}
 24 |     TestStatus -->|"Yes"| TestSuccess["Minimal Build Test<br>✅ PASS"]
 25 |     TestStatus -->|"No"| FixTest["Fix Test<br>Issues"]
 26 |     FixTest --> RetryTest["Retry Test"]
 27 |     RetryTest --> TestStatus
 28 | ```
 29 | 
 30 | ### Minimal Build Test Implementation:
 31 | ```powershell
 32 | # Example: Perform minimal build test for a React project
 33 | function Perform-MinimalBuildTest {
 34 |     $buildSuccess = $false
 35 |     $testSuccess = $false
 36 |     
 37 |     # Create minimal test project
 38 |     $testDir = ".__build_test"
 39 |     if (Test-Path $testDir) {
 40 |         Remove-Item -Path $testDir -Recurse -Force
 41 |     }
 42 |     
 43 |     try {
 44 |         # Create minimal test directory
 45 |         New-Item -Path $testDir -ItemType Directory | Out-Null
 46 |         Push-Location $testDir
 47 |         
 48 |         # Initialize minimal package.json
 49 |         @"
 50 | {
 51 |   "name": "build-test",
 52 |   "version": "1.0.0",
 53 |   "description": "Minimal build test",
 54 |   "main": "index.js",
 55 |   "scripts": {
 56 |     "build": "echo Build test successful"
 57 |   }
 58 | }
 59 | "@ | Set-Content -Path "package.json"
 60 |         
 61 |         # Attempt build
 62 |         npm run build | Out-Null
 63 |         $buildSuccess = $true
 64 |         
 65 |         # Create minimal test file
 66 |         @"
 67 | console.log('Test successful');
 68 | "@ | Set-Content -Path "index.js"
 69 |         
 70 |         # Run basic test
 71 |         node index.js | Out-Null
 72 |         $testSuccess = $true
 73 |         
 74 |     } catch {
 75 |         Write-Output "❌ Build test failed: $($_.Exception.Message)"
 76 |     } finally {
 77 |         Pop-Location
 78 |         if (Test-Path $testDir) {
 79 |             Remove-Item -Path $testDir -Recurse -Force
 80 |         }
 81 |     }
 82 |     
 83 |     # Display results
 84 |     if ($buildSuccess -and $testSuccess) {
 85 |         Write-Output "✅ Minimal build test passed successfully"
 86 |         return $true
 87 |     } else {
 88 |         if (-not $buildSuccess) {
 89 |             Write-Output "❌ Build process failed"
 90 |         }
 91 |         if (-not $testSuccess) {
 92 |             Write-Output "❌ Basic functionality test failed"
 93 |         }
 94 |         return $false
 95 |     }
 96 | }
 97 | ```
 98 | 
 99 | ## 📋 MINIMAL BUILD TEST CHECKPOINT
100 | 
101 | ```
102 | ✓ CHECKPOINT: MINIMAL BUILD TEST
103 | - Test project creation successful? [YES/NO]
104 | - Build process completed successfully? [YES/NO]
105 | - Basic functionality test passed? [YES/NO]
106 | 
107 | → If all YES: QA Validation complete, proceed to generate success report.
108 | → If any NO: Fix build issues before continuing.
109 | ```
110 | 
111 | **Next Step (on PASS):** Load `van-qa-utils/reports.mdc` to generate success report.
112 | **Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for build test fixes. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-checks/config-check.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Process map for VAN QA configuration validation
 3 | globs: van-qa-checks/config-check.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN QA: CONFIGURATION VALIDATION
 7 | 
 8 | > **TL;DR:** This component validates configuration files for proper syntax and compatibility with the project and platform.
 9 | 
10 | ## 2️⃣ CONFIGURATION VALIDATION PROCESS
11 | 
12 | ```mermaid
13 | graph TD
14 |     Start["Configuration Validation"] --> IdentifyConfigs["Identify Configuration<br>Files"]
15 |     IdentifyConfigs --> ReadConfigs["Read Configuration<br>Files"]
16 |     ReadConfigs --> ValidateSyntax["Validate Syntax<br>and Format"]
17 |     ValidateSyntax --> SyntaxStatus{"Syntax<br>Valid?"}
18 |     
19 |     SyntaxStatus -->|"Yes"| CheckCompatibility["Check Compatibility<br>with Platform"]
20 |     SyntaxStatus -->|"No"| FixSyntax["Fix Syntax<br>Errors"]
21 |     FixSyntax --> RetryValidate["Retry Validation"]
22 |     RetryValidate --> SyntaxStatus
23 |     
24 |     CheckCompatibility --> CompatStatus{"Compatible with<br>Platform?"}
25 |     CompatStatus -->|"Yes"| ConfigSuccess["Configurations Validated<br>✅ PASS"]
26 |     CompatStatus -->|"No"| AdaptConfigs["Adapt Configurations<br>for Platform"]
27 |     AdaptConfigs --> RetryCompat["Retry Compatibility<br>Check"]
28 |     RetryCompat --> CompatStatus
29 | ```
30 | 
31 | ### Configuration Validation Implementation:
32 | ```powershell
33 | # Example: Validate configuration files for a web project
34 | function Validate-Configurations {
35 |     $configFiles = @(
36 |         "package.json",
37 |         "tsconfig.json",
38 |         "vite.config.js"
39 |     )
40 |     
41 |     $invalidConfigs = @()
42 |     $incompatibleConfigs = @()
43 |     
44 |     foreach ($configFile in $configFiles) {
45 |         if (Test-Path $configFile) {
46 |             # Check JSON syntax for JSON files
47 |             if ($configFile -match "\.json

quot;) {
48 |                 try {
49 |                     Get-Content $configFile -Raw | ConvertFrom-Json | Out-Null
50 |                 } catch {
51 |                     $invalidConfigs += "$configFile (JSON syntax error: $($_.Exception.Message))"
52 |                     continue
53 |                 }
54 |             }
55 |             
56 |             # Specific configuration compatibility checks
57 |             if ($configFile -eq "vite.config.js") {
58 |                 $content = Get-Content $configFile -Raw
59 |                 # Check for React plugin in Vite config
60 |                 if ($content -notmatch "react\(\)") {
61 |                     $incompatibleConfigs += "$configFile (Missing React plugin for React project)"
62 |                 }
63 |             }
64 |         } else {
65 |             $invalidConfigs += "$configFile (file not found)"
66 |         }
67 |     }
68 |     
69 |     # Display results
70 |     if ($invalidConfigs.Count -eq 0 -and $incompatibleConfigs.Count -eq 0) {
71 |         Write-Output "✅ All configurations validated and compatible"
72 |         return $true
73 |     } else {
74 |         if ($invalidConfigs.Count -gt 0) {
75 |             Write-Output "❌ Invalid configurations: $($invalidConfigs -join ', ')"
76 |         }
77 |         if ($incompatibleConfigs.Count -gt 0) {
78 |             Write-Output "❌ Incompatible configurations: $($incompatibleConfigs -join ', ')"
79 |         }
80 |         return $false
81 |     }
82 | }
83 | ```
84 | 
85 | ## 📋 CONFIGURATION VALIDATION CHECKPOINT
86 | 
87 | ```
88 | ✓ CHECKPOINT: CONFIGURATION VALIDATION
89 | - All configuration files found? [YES/NO]
90 | - All configuration syntax valid? [YES/NO]
91 | - All configurations compatible with platform? [YES/NO]
92 | 
93 | → If all YES: Continue to Environment Validation.
94 | → If any NO: Fix configuration issues before continuing.
95 | ```
96 | 
97 | **Next Step (on PASS):** Load `van-qa-checks/environment-check.mdc`.
98 | **Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for configuration fixes. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-checks/dependency-check.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Process map for VAN QA dependency verification
  3 | globs: van-qa-checks/dependency-check.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # VAN QA: DEPENDENCY VERIFICATION
  7 | 
  8 | > **TL;DR:** This component verifies that all required dependencies are installed and compatible with the project requirements.
  9 | 
 10 | ## 1️⃣ DEPENDENCY VERIFICATION PROCESS
 11 | 
 12 | ```mermaid
 13 | graph TD
 14 |     Start["Dependency Verification"] --> ReadDeps["Read Required Dependencies<br>from Creative Phase"]
 15 |     ReadDeps --> CheckInstalled["Check if Dependencies<br>are Installed"]
 16 |     CheckInstalled --> DepStatus{"All Dependencies<br>Installed?"}
 17 |     
 18 |     DepStatus -->|"Yes"| VerifyVersions["Verify Versions<br>and Compatibility"]
 19 |     DepStatus -->|"No"| InstallMissing["Install Missing<br>Dependencies"]
 20 |     InstallMissing --> VerifyVersions
 21 |     
 22 |     VerifyVersions --> VersionStatus{"Versions<br>Compatible?"}
 23 |     VersionStatus -->|"Yes"| DepSuccess["Dependencies Verified<br>✅ PASS"]
 24 |     VersionStatus -->|"No"| UpgradeVersions["Upgrade/Downgrade<br>as Needed"]
 25 |     UpgradeVersions --> RetryVerify["Retry Verification"]
 26 |     RetryVerify --> VersionStatus
 27 | ```
 28 | 
 29 | ### Windows (PowerShell) Implementation:
 30 | ```powershell
 31 | # Example: Verify Node.js dependencies for a React project
 32 | function Verify-Dependencies {
 33 |     $requiredDeps = @{ "node" = ">=14.0.0"; "npm" = ">=6.0.0" }
 34 |     $missingDeps = @(); $incompatibleDeps = @()
 35 |     
 36 |     # Check Node.js version
 37 |     try { 
 38 |         $nodeVersion = node -v
 39 |         if ($nodeVersion -match "v(\d+)\.(\d+)\.(\d+)") {
 40 |             $major = [int]$Matches[1]
 41 |             if ($major -lt 14) {
 42 |                 $incompatibleDeps += "node (found $nodeVersion, required >=14.0.0)"
 43 |             }
 44 |         }
 45 |     } catch {
 46 |         $missingDeps += "node"
 47 |     }
 48 |     
 49 |     # Check npm version
 50 |     try { 
 51 |         $npmVersion = npm -v
 52 |         if ($npmVersion -match "(\d+)\.(\d+)\.(\d+)") {
 53 |             $major = [int]$Matches[1]
 54 |             if ($major -lt 6) {
 55 |                 $incompatibleDeps += "npm (found $npmVersion, required >=6.0.0)"
 56 |             }
 57 |         }
 58 |     } catch {
 59 |         $missingDeps += "npm"
 60 |     }
 61 |     
 62 |     # Display results
 63 |     if ($missingDeps.Count -eq 0 -and $incompatibleDeps.Count -eq 0) {
 64 |         Write-Output "✅ All dependencies verified and compatible"
 65 |         return $true
 66 |     } else {
 67 |         if ($missingDeps.Count -gt 0) {
 68 |             Write-Output "❌ Missing dependencies: $($missingDeps -join ', ')"
 69 |         }
 70 |         if ($incompatibleDeps.Count -gt 0) {
 71 |             Write-Output "❌ Incompatible versions: $($incompatibleDeps -join ', ')"
 72 |         }
 73 |         return $false
 74 |     }
 75 | }
 76 | ```
 77 | 
 78 | ### Mac/Linux (Bash) Implementation:
 79 | ```bash
 80 | #!/bin/bash
 81 | 
 82 | # Example: Verify Node.js dependencies for a React project
 83 | verify_dependencies() {
 84 |     local missing_deps=()
 85 |     local incompatible_deps=()
 86 |     
 87 |     # Check Node.js version
 88 |     if command -v node &> /dev/null; then
 89 |         local node_version=$(node -v)
 90 |         if [[ $node_version =~ v([0-9]+)\.([0-9]+)\.([0-9]+) ]]; then
 91 |             local major=${BASH_REMATCH[1]}
 92 |             if (( major < 14 )); then
 93 |                 incompatible_deps+=("node (found $node_version, required >=14.0.0)")
 94 |             fi
 95 |         fi
 96 |     else
 97 |         missing_deps+=("node")
 98 |     fi
 99 |     
100 |     # Check npm version
101 |     if command -v npm &> /dev/null; then
102 |         local npm_version=$(npm -v)
103 |         if [[ $npm_version =~ ([0-9]+)\.([0-9]+)\.([0-9]+) ]]; then
104 |             local major=${BASH_REMATCH[1]}
105 |             if (( major < 6 )); then
106 |                 incompatible_deps+=("npm (found $npm_version, required >=6.0.0)")
107 |             fi
108 |         fi
109 |     else
110 |         missing_deps+=("npm")
111 |     fi
112 |     
113 |     # Display results
114 |     if [ ${#missing_deps[@]} -eq 0 ] && [ ${#incompatible_deps[@]} -eq 0 ]; then
115 |         echo "✅ All dependencies verified and compatible"
116 |         return 0
117 |     else
118 |         if [ ${#missing_deps[@]} -gt 0 ]; then
119 |             echo "❌ Missing dependencies: ${missing_deps[*]}"
120 |         fi
121 |         if [ ${#incompatible_deps[@]} -gt 0 ]; then
122 |             echo "❌ Incompatible versions: ${incompatible_deps[*]}"
123 |         fi
124 |         return 1
125 |     fi
126 | }
127 | ```
128 | 
129 | ## 📋 DEPENDENCY VERIFICATION CHECKPOINT
130 | 
131 | ```
132 | ✓ CHECKPOINT: DEPENDENCY VERIFICATION
133 | - Required dependencies identified? [YES/NO]
134 | - All dependencies installed? [YES/NO]
135 | - All versions compatible? [YES/NO]
136 | 
137 | → If all YES: Continue to Configuration Validation.
138 | → If any NO: Fix dependency issues before continuing.
139 | ```
140 | 
141 | **Next Step (on PASS):** Load `van-qa-checks/config-check.mdc`.
142 | **Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for dependency fixes. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-checks/environment-check.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Process map for VAN QA environment validation
 3 | globs: van-qa-checks/environment-check.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN QA: ENVIRONMENT VALIDATION
 7 | 
 8 | > **TL;DR:** This component verifies that the build environment is properly set up with required tools and permissions.
 9 | 
10 | ## 3️⃣ ENVIRONMENT VALIDATION PROCESS
11 | 
12 | ```mermaid
13 | graph TD
14 |     Start["Environment Validation"] --> CheckEnv["Check Build Environment"]
15 |     CheckEnv --> VerifyBuildTools["Verify Build Tools"]
16 |     VerifyBuildTools --> ToolsStatus{"Build Tools<br>Available?"}
17 |     
18 |     ToolsStatus -->|"Yes"| CheckPerms["Check Permissions<br>and Access"]
19 |     ToolsStatus -->|"No"| InstallTools["Install Required<br>Build Tools"]
20 |     InstallTools --> RetryTools["Retry Verification"]
21 |     RetryTools --> ToolsStatus
22 |     
23 |     CheckPerms --> PermsStatus{"Permissions<br>Sufficient?"}
24 |     PermsStatus -->|"Yes"| EnvSuccess["Environment Validated<br>✅ PASS"]
25 |     PermsStatus -->|"No"| FixPerms["Fix Permission<br>Issues"]
26 |     FixPerms --> RetryPerms["Retry Permission<br>Check"]
27 |     RetryPerms --> PermsStatus
28 | ```
29 | 
30 | ### Environment Validation Implementation:
31 | ```powershell
32 | # Example: Validate environment for a web project
33 | function Validate-Environment {
34 |     $requiredTools = @(
35 |         @{Name = "git"; Command = "git --version"},
36 |         @{Name = "node"; Command = "node --version"},
37 |         @{Name = "npm"; Command = "npm --version"}
38 |     )
39 |     
40 |     $missingTools = @()
41 |     $permissionIssues = @()
42 |     
43 |     # Check build tools
44 |     foreach ($tool in $requiredTools) {
45 |         try {
46 |             Invoke-Expression $tool.Command | Out-Null
47 |         } catch {
48 |             $missingTools += $tool.Name
49 |         }
50 |     }
51 |     
52 |     # Check write permissions in project directory
53 |     try {
54 |         $testFile = ".__permission_test"
55 |         New-Item -Path $testFile -ItemType File -Force | Out-Null
56 |         Remove-Item -Path $testFile -Force
57 |     } catch {
58 |         $permissionIssues += "Current directory (write permission denied)"
59 |     }
60 |     
61 |     # Check if port 3000 is available (commonly used for dev servers)
62 |     try {
63 |         $listener = New-Object System.Net.Sockets.TcpListener([System.Net.IPAddress]::Loopback, 3000)
64 |         $listener.Start()
65 |         $listener.Stop()
66 |     } catch {
67 |         $permissionIssues += "Port 3000 (already in use or access denied)"
68 |     }
69 |     
70 |     # Display results
71 |     if ($missingTools.Count -eq 0 -and $permissionIssues.Count -eq 0) {
72 |         Write-Output "✅ Environment validated successfully"
73 |         return $true
74 |     } else {
75 |         if ($missingTools.Count -gt 0) {
76 |             Write-Output "❌ Missing tools: $($missingTools -join ', ')"
77 |         }
78 |         if ($permissionIssues.Count -gt 0) {
79 |             Write-Output "❌ Permission issues: $($permissionIssues -join ', ')"
80 |         }
81 |         return $false
82 |     }
83 | }
84 | ```
85 | 
86 | ## 📋 ENVIRONMENT VALIDATION CHECKPOINT
87 | 
88 | ```
89 | ✓ CHECKPOINT: ENVIRONMENT VALIDATION
90 | - All required build tools installed? [YES/NO]
91 | - Project directory permissions sufficient? [YES/NO]
92 | - Required ports available? [YES/NO]
93 | 
94 | → If all YES: Continue to Minimal Build Test.
95 | → If any NO: Fix environment issues before continuing.
96 | ```
97 | 
98 | **Next Step (on PASS):** Load `van-qa-checks/build-test.mdc`.
99 | **Next Step (on FAIL):** Check `van-qa-utils/common-fixes.mdc` for environment fixes. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-checks/file-verification.mdc:
--------------------------------------------------------------------------------
1 |  


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-main.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Visual process map for VAN QA mode (Technical Validation Entry Point)
  3 | globs: van-qa-main.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # VAN MODE: QA TECHNICAL VALIDATION (Main Entry)
  7 | 
  8 | > **TL;DR:** This is the entry point for the QA validation process that executes *after* CREATIVE mode and *before* BUILD mode. It ensures technical requirements are met before implementation begins.
  9 | 
 10 | ## 📣 HOW TO USE THESE QA RULES
 11 | 
 12 | To access any QA validation rule or component, use the `fetch_rules` tool with exact rule names:
 13 | 
 14 | ```
 15 | // CRITICAL: Always use fetch_rules to load validation components
 16 | // For detailed examples and guidance, load:
 17 | // isolation_rules/visual-maps/van-qa-utils/rule-calling-guide
 18 | ```
 19 | 
 20 | ## 🚀 VAN QA MODE ACTIVATION
 21 | 
 22 | After completing CREATIVE mode, when the user types "VAN QA", respond:
 23 | 
 24 | ```mermaid
 25 | graph TD
 26 |     UserQA["User Types: QA"] --> HighPriority["⚠️ HIGH PRIORITY COMMAND"]
 27 |     HighPriority --> CurrentTask["Pause Current Task/Process"]
 28 |     CurrentTask --> LoadQA["Load QA Main Map (This File)"]
 29 |     LoadQA --> RunQA["Execute QA Validation Process"]
 30 |     RunQA --> QAResults{"QA Results"}
 31 |     
 32 |     QAResults -->|"PASS"| ResumeFlow["Resume Prior Process Flow"]
 33 |     QAResults -->|"FAIL"| FixIssues["Fix Identified Issues"]
 34 |     FixIssues --> ReRunQA["Re-run QA Validation"]
 35 |     ReRunQA --> QAResults
 36 | ```
 37 | 
 38 | ### QA Interruption Rules
 39 | 
 40 | 1. **Immediate Precedence:** `QA` command interrupts everything.
 41 | 2. **Load & Execute:** Load this map (`van-qa-main.mdc`) and its components (see below).
 42 | 3. **Remediation Priority:** Fixes take priority over pending mode switches.
 43 | 4. **Resume:** On PASS, resume the previous flow.
 44 | 
 45 | ```
 46 | ⚠️ QA OVERRIDE ACTIVATED
 47 | All other processes paused
 48 | QA validation checks now running...
 49 | Any issues found MUST be remediated before continuing with normal process flow
 50 | ```
 51 | 
 52 | ## 🔍 TECHNICAL VALIDATION OVERVIEW
 53 | 
 54 | Four-point validation process with selective loading:
 55 | 
 56 | ```mermaid
 57 | graph TD
 58 |     VANQA["VAN QA MODE"] --> FourChecks["FOUR-POINT VALIDATION"]
 59 |     
 60 |     FourChecks --> DepCheck["1️⃣ DEPENDENCY VERIFICATION
 61 |     Load: van-qa-checks/dependency-check.mdc"]
 62 |     DepCheck --> ConfigCheck["2️⃣ CONFIGURATION VALIDATION
 63 |     Load: van-qa-checks/config-check.mdc"]
 64 |     ConfigCheck --> EnvCheck["3️⃣ ENVIRONMENT VALIDATION
 65 |     Load: van-qa-checks/environment-check.mdc"]
 66 |     EnvCheck --> MinBuildCheck["4️⃣ MINIMAL BUILD TEST
 67 |     Load: van-qa-checks/build-test.mdc"]
 68 |     
 69 |     MinBuildCheck --> ValidationResults{"All Checks<br>Passed?"}
 70 |     ValidationResults -->|"Yes"| SuccessReport["GENERATE SUCCESS REPORT
 71 |     Load: van-qa-utils/reports.mdc"]
 72 |     ValidationResults -->|"No"| FailureReport["GENERATE FAILURE REPORT
 73 |     Load: van-qa-utils/reports.mdc"]
 74 |     
 75 |     SuccessReport --> BUILD_Transition["Trigger BUILD Mode
 76 |     Load: van-qa-utils/mode-transitions.mdc"]
 77 |     FailureReport --> FixIssues["Fix Technical Issues
 78 |     Load: van-qa-utils/common-fixes.mdc"]
 79 |     FixIssues --> ReValidate["Re-validate (Re-run VAN QA)"]
 80 |     ReValidate --> FourChecks
 81 | ```
 82 | 
 83 | ## 🔄 INTEGRATION WITH DESIGN DECISIONS
 84 | 
 85 | Reads Creative Phase outputs to inform validation:
 86 | 
 87 | ```mermaid
 88 | graph TD
 89 |     Start["Read Design Decisions"] --> ReadCreative["Parse Creative Phase<br>Documentation"]
 90 |     ReadCreative --> ExtractTech["Extract Technology<br>Choices"]
 91 |     ExtractTech --> ExtractDeps["Extract Required<br>Dependencies"]
 92 |     ExtractDeps --> BuildValidationPlan["Build Validation<br>Plan"]
 93 |     BuildValidationPlan --> StartValidation["Start Four-Point<br>Validation Process"]
 94 | ```
 95 | 
 96 | ## 📋 COMPONENT LOADING SEQUENCE
 97 | 
 98 | The QA validation process follows this selective loading sequence:
 99 | 
100 | 1. **Main Entry (This File)**: `van-qa-main.mdc`
101 | 2. **Validation Checks**:
102 |    - `van-qa-checks/dependency-check.mdc`
103 |    - `van-qa-checks/config-check.mdc`
104 |    - `van-qa-checks/environment-check.mdc`
105 |    - `van-qa-checks/build-test.mdc`
106 | 3. **Utilities (As Needed)**:
107 |    - `van-qa-utils/reports.mdc`
108 |    - `van-qa-utils/common-fixes.mdc`
109 |    - `van-qa-utils/mode-transitions.mdc`
110 | 
111 | ## 📋 FINAL QA VALIDATION CHECKPOINT
112 | 
113 | ```
114 | ✓ SECTION CHECKPOINT: QA VALIDATION
115 | - Dependency Verification Passed? [YES/NO]
116 | - Configuration Validation Passed? [YES/NO]
117 | - Environment Validation Passed? [YES/NO]
118 | - Minimal Build Test Passed? [YES/NO]
119 | 
120 | → If all YES: Ready for BUILD mode transition.
121 | → If any NO: Fix identified issues and re-run VAN QA.
122 | ```
123 | 
124 | **Next Step (on PASS):** Trigger BUILD mode (load `van-qa-utils/mode-transitions.mdc`).
125 | **Next Step (on FAIL):** Address issues (load `van-qa-utils/common-fixes.mdc`) and re-run `VAN QA`. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-utils/common-fixes.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Utility for VAN QA common validation fixes
 3 | globs: van-qa-utils/common-fixes.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN QA: COMMON VALIDATION FIXES
 7 | 
 8 | > **TL;DR:** This component provides common fixes for issues that may arise during the QA validation process.
 9 | 
10 | ## 🧪 COMMON QA VALIDATION FIXES BY CATEGORY
11 | 
12 | ### Dependency Issues
13 | 
14 | | Issue | Fix |
15 | |-------|-----|
16 | | **Missing Node.js** | Download and install Node.js from https://nodejs.org/ |
17 | | **Outdated npm** | Run `npm install -g npm@latest` to update |
18 | | **Missing packages** | Run `npm install` or `npm install [package-name]` |
19 | | **Package version conflicts** | Adjust versions in package.json and run `npm install` |
20 | | **Dependency resolution issues** | Run `npm cache clean -f` and try installing again |
21 | 
22 | ### Configuration Issues
23 | 
24 | | Issue | Fix |
25 | |-------|-----|
26 | | **Invalid JSON** | Use a JSON validator (e.g., jsonlint) to check syntax |
27 | | **Missing React plugin** | Add `import react from '@vitejs/plugin-react'` and `plugins: [react()]` to vite.config.js |
28 | | **Incompatible TypeScript config** | Update `tsconfig.json` with correct React settings |
29 | | **Mismatched version references** | Ensure consistent versions across configuration files |
30 | | **Missing entries in config files** | Add required fields to configuration files |
31 | 
32 | ### Environment Issues
33 | 
34 | | Issue | Fix |
35 | |-------|-----|
36 | | **Permission denied** | Run terminal as administrator (Windows) or use sudo (Mac/Linux) |
37 | | **Port already in use** | Kill process using the port: `netstat -ano \| findstr :PORT` then `taskkill /F /PID PID` (Windows) or `lsof -i :PORT` then `kill -9 PID` (Mac/Linux) |
38 | | **Missing build tools** | Install required command-line tools (git, node, etc.) |
39 | | **Environment variable issues** | Set required environment variables: `$env:VAR_NAME = "value"` (PowerShell) or `export VAR_NAME="value"` (Bash) |
40 | | **Disk space issues** | Free up disk space, clean npm/package cache files |
41 | 
42 | ### Build Test Issues
43 | 
44 | | Issue | Fix |
45 | |-------|-----|
46 | | **Build fails** | Check console for specific error messages |
47 | | **Test fails** | Verify minimal configuration is correct |
48 | | **Path issues** | Ensure paths use correct separators for the platform (`\` for Windows, `/` for Mac/Linux) |
49 | | **Missing dependencies** | Make sure all required dependencies are installed |
50 | | **Script permissions** | Ensure script files have execution permissions (chmod +x on Unix) |
51 | 
52 | ## 📝 ISSUE DIAGNOSIS PROCEDURES
53 | 
54 | ### 1. Dependency Diagnosis
55 | ```powershell
56 | # Find conflicting dependencies
57 | npm ls [package-name]
58 | 
59 | # Check for outdated packages
60 | npm outdated
61 | 
62 | # Check for vulnerabilities
63 | npm audit
64 | ```
65 | 
66 | ### 2. Configuration Diagnosis
67 | ```powershell
68 | # List all configuration files
69 | Get-ChildItem -Recurse -Include "*.json","*.config.js" | Select-Object FullName
70 | 
71 | # Find missing references in tsconfig.json
72 | if (Test-Path "tsconfig.json") { 
73 |     $tsconfig = Get-Content "tsconfig.json" -Raw | ConvertFrom-Json
74 |     if (-not $tsconfig.compilerOptions.jsx) {
75 |         Write-Output "Missing jsx setting in tsconfig.json"
76 |     }
77 | }
78 | ```
79 | 
80 | ### 3. Environment Diagnosis
81 | ```powershell
82 | # Check process using a port (Windows)
83 | netstat -ano | findstr ":3000"
84 | 
85 | # List environment variables
86 | Get-ChildItem Env:
87 | 
88 | # Check disk space
89 | Get-PSDrive C | Select-Object Used,Free
90 | ```
91 | 
92 | **Next Step:** Return to the validation process or follow the specific fix recommendations provided above. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-utils/mode-transitions.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Utility for VAN QA mode transitions
 3 | globs: van-qa-utils/mode-transitions.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN QA: MODE TRANSITIONS
 7 | 
 8 | > **TL;DR:** This component handles transitions between modes, particularly the QA validation to BUILD mode transition, and prevents BUILD mode access without successful QA validation.
 9 | 
10 | ## 🔒 BUILD MODE PREVENTION MECHANISM
11 | 
12 | The system prevents moving to BUILD mode without passing QA validation:
13 | 
14 | ```mermaid
15 | graph TD
16 |     Start["User Types: BUILD"] --> CheckQA{"QA Validation<br>Completed?"}
17 |     CheckQA -->|"Yes and Passed"| AllowBuild["Allow BUILD Mode"]
18 |     CheckQA -->|"No or Failed"| BlockBuild["BLOCK BUILD MODE"]
19 |     BlockBuild --> Message["Display:<br>⚠️ QA VALIDATION REQUIRED"]
20 |     Message --> ReturnToVANQA["Prompt: Type VAN QA"]
21 | ```
22 | 
23 | ### Implementation Example (PowerShell):
24 | ```powershell
25 | # Check QA status before allowing BUILD mode
26 | function Check-QAValidationStatus {
27 |     $qaStatusFile = "documentation\memory-bank\.qa_validation_status" # Assumes status is written by reports.mdc
28 |     
29 |     if (Test-Path $qaStatusFile) {
30 |         $status = Get-Content $qaStatusFile -Raw
31 |         if ($status -match "PASS") {
32 |             return $true
33 |         }
34 |     }
35 |     
36 |     # Display block message
37 |     Write-Output "`n`n"
38 |     Write-Output "🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫"
39 |     Write-Output "⛔️ BUILD MODE BLOCKED: QA VALIDATION REQUIRED"
40 |     Write-Output "⛔️ You must complete QA validation before proceeding to BUILD mode"
41 |     Write-Output "`n"
42 |     Write-Output "Type 'VAN QA' to perform technical validation"
43 |     Write-Output "`n"
44 |     Write-Output "🚫 NO IMPLEMENTATION CAN PROCEED WITHOUT VALIDATION 🚫"
45 |     Write-Output "🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫🚫"
46 |     
47 |     return $false
48 | }
49 | ```
50 | 
51 | ## 🚨 MODE TRANSITION TRIGGERS
52 | 
53 | ### CREATIVE to VAN QA Transition:
54 | After completing the CREATIVE phase, trigger this message to prompt QA validation:
55 | 
56 | ```
57 | ⏭️ NEXT MODE: VAN QA
58 | To validate technical requirements before implementation, please type 'VAN QA'
59 | ```
60 | 
61 | ### VAN QA to BUILD Transition (On Success):
62 | After successful QA validation, trigger this message to allow BUILD mode:
63 | 
64 | ```
65 | ✅ TECHNICAL VALIDATION COMPLETE
66 | All prerequisites verified successfully
67 | You may now proceed to BUILD mode
68 | Type 'BUILD' to begin implementation
69 | ```
70 | 
71 | ### Manual BUILD Mode Access (When QA Already Passed):
72 | When the user manually types 'BUILD', check the QA status before allowing access:
73 | 
74 | ```powershell
75 | # Handle BUILD mode request
76 | function Handle-BuildModeRequest {
77 |     if (Check-QAValidationStatus) {
78 |         # Allow transition to BUILD mode
79 |         Write-Output "`n"
80 |         Write-Output "✅ QA VALIDATION CHECK: PASSED"
81 |         Write-Output "Loading BUILD mode..."
82 |         Write-Output "`n"
83 |         
84 |         # Here you would load the BUILD mode map
85 |         # [Code to load BUILD mode map]
86 |         
87 |         return $true
88 |     }
89 |     
90 |     # QA validation failed or not completed, BUILD mode blocked
91 |     return $false
92 | }
93 | ```
94 | 
95 | **Next Step (on QA SUCCESS):** Continue to BUILD mode.
96 | **Next Step (on QA FAILURE):** Return to QA validation process. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-utils/reports.mdc:
--------------------------------------------------------------------------------
  1 | ---
  2 | description: Utility for VAN QA validation reports
  3 | globs: van-qa-utils/reports.mdc
  4 | alwaysApply: false
  5 | ---
  6 | # VAN QA: VALIDATION REPORTS
  7 | 
  8 | > **TL;DR:** This component contains the formats for comprehensive success and failure reports generated upon completion of the QA validation process.
  9 | 
 10 | ## 📋 COMPREHENSIVE SUCCESS REPORT FORMAT
 11 | 
 12 | After all four validation points pass, generate this success report:
 13 | 
 14 | ```
 15 | ╔═════════════════════ 🔍 QA VALIDATION REPORT ══════════════════════╗
 16 | │ PROJECT: [Project Name] | TIMESTAMP: [Current Date/Time]            │
 17 | ├─────────────────────────────────────────────────────────────────────┤
 18 | │ 1️⃣ DEPENDENCIES: ✓ Compatible                                       │
 19 | │ 2️⃣ CONFIGURATION: ✓ Valid & Compatible                             │
 20 | │ 3️⃣ ENVIRONMENT: ✓ Ready                                             │
 21 | │ 4️⃣ MINIMAL BUILD: ✓ Successful & Passed                            │
 22 | ├─────────────────────────────────────────────────────────────────────┤
 23 | │ 🚨 FINAL VERDICT: PASS                                              │
 24 | │ ➡️ Clear to proceed to BUILD mode                                   │
 25 | ╚═════════════════════════════════════════════════════════════════════╝
 26 | ```
 27 | 
 28 | ### Success Report Generation Example:
 29 | ```powershell
 30 | function Generate-SuccessReport {
 31 |     param (
 32 |         [string]$ProjectName = "Current Project"
 33 |     )
 34 |     
 35 |     $timestamp = Get-Date -Format "yyyy-MM-dd HH:mm:ss"
 36 |     
 37 |     $report = @"
 38 | ╔═════════════════════ 🔍 QA VALIDATION REPORT ══════════════════════╗
 39 | │ PROJECT: $ProjectName | TIMESTAMP: $timestamp            │
 40 | ├─────────────────────────────────────────────────────────────────────┤
 41 | │ 1️⃣ DEPENDENCIES: ✓ Compatible                                       │
 42 | │ 2️⃣ CONFIGURATION: ✓ Valid & Compatible                             │
 43 | │ 3️⃣ ENVIRONMENT: ✓ Ready                                             │
 44 | │ 4️⃣ MINIMAL BUILD: ✓ Successful & Passed                            │
 45 | ├─────────────────────────────────────────────────────────────────────┤
 46 | │ 🚨 FINAL VERDICT: PASS                                              │
 47 | │ ➡️ Clear to proceed to BUILD mode                                   │
 48 | ╚═════════════════════════════════════════════════════════════════════╝
 49 | "@
 50 |     
 51 |     # Save validation status (used by BUILD mode prevention mechanism)
 52 |     "PASS" | Set-Content -Path "documentation\memory-bank\.qa_validation_status"
 53 |     
 54 |     return $report
 55 | }
 56 | ```
 57 | 
 58 | ## ❌ FAILURE REPORT FORMAT
 59 | 
 60 | If any validation step fails, generate this detailed failure report:
 61 | 
 62 | ```
 63 | ⚠️⚠️⚠️ QA VALIDATION FAILED ⚠️⚠️⚠️
 64 | 
 65 | The following issues must be resolved before proceeding to BUILD mode:
 66 | 
 67 | 1️⃣ DEPENDENCY ISSUES:
 68 | - [Detailed description of dependency issues]
 69 | - [Recommended fix]
 70 | 
 71 | 2️⃣ CONFIGURATION ISSUES:
 72 | - [Detailed description of configuration issues]
 73 | - [Recommended fix]
 74 | 
 75 | 3️⃣ ENVIRONMENT ISSUES:
 76 | - [Detailed description of environment issues]
 77 | - [Recommended fix]
 78 | 
 79 | 4️⃣ BUILD TEST ISSUES:
 80 | - [Detailed description of build test issues]
 81 | - [Recommended fix]
 82 | 
 83 | ⚠️ BUILD MODE IS BLOCKED until these issues are resolved.
 84 | Type 'VAN QA' after fixing the issues to re-validate.
 85 | ```
 86 | 
 87 | ### Failure Report Generation Example:
 88 | ```powershell
 89 | function Generate-FailureReport {
 90 |     param (
 91 |         [string[]]$DependencyIssues = @(),
 92 |         [string[]]$ConfigIssues = @(),
 93 |         [string[]]$EnvironmentIssues = @(),
 94 |         [string[]]$BuildIssues = @()
 95 |     )
 96 |     
 97 |     $report = @"
 98 | ⚠️⚠️⚠️ QA VALIDATION FAILED ⚠️⚠️⚠️
 99 | 
100 | The following issues must be resolved before proceeding to BUILD mode:
101 | 
102 | "@
103 |     
104 |     if ($DependencyIssues.Count -gt 0) {
105 |         $report += @"
106 | 1️⃣ DEPENDENCY ISSUES:
107 | $(($DependencyIssues | ForEach-Object { "- $_" }) -join "`n")
108 | 
109 | "@
110 |     }
111 |     
112 |     if ($ConfigIssues.Count -gt 0) {
113 |         $report += @"
114 | 2️⃣ CONFIGURATION ISSUES:
115 | $(($ConfigIssues | ForEach-Object { "- $_" }) -join "`n")
116 | 
117 | "@
118 |     }
119 |     
120 |     if ($EnvironmentIssues.Count -gt 0) {
121 |         $report += @"
122 | 3️⃣ ENVIRONMENT ISSUES:
123 | $(($EnvironmentIssues | ForEach-Object { "- $_" }) -join "`n")
124 | 
125 | "@
126 |     }
127 |     
128 |     if ($BuildIssues.Count -gt 0) {
129 |         $report += @"
130 | 4️⃣ BUILD TEST ISSUES:
131 | $(($BuildIssues | ForEach-Object { "- $_" }) -join "`n")
132 | 
133 | "@
134 |     }
135 |     
136 |     $report += @"
137 | ⚠️ BUILD MODE IS BLOCKED until these issues are resolved.
138 | Type 'VAN QA' after fixing the issues to re-validate.
139 | "@
140 |     
141 |     # Save validation status (used by BUILD mode prevention mechanism)
142 |     "FAIL" | Set-Content -Path "documentation\memory-bank\.qa_validation_status"
143 |     
144 |     return $report
145 | }
146 | ```
147 | 
148 | **Next Step (on SUCCESS):** Load `van-qa-utils/mode-transitions.mdc` to handle BUILD mode transition.
149 | **Next Step (on FAILURE):** Load `van-qa-utils/common-fixes.mdc` for issue remediation guidance. 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-utils/rule-calling-guide.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Comprehensive guide for calling VAN QA rules
 3 | globs: van-qa-utils/rule-calling-guide.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN QA: COMPREHENSIVE RULE CALLING GUIDE
 7 | 
 8 | > **TL;DR:** This reference guide shows how to properly call all VAN QA rules at the right time during the validation process.
 9 | 
10 | ## 🔍 RULE CALLING BASICS
11 | 
12 | Remember these key principles:
13 | 1. Always use the `fetch_rules` tool to load rules
14 | 2. Use exact rule paths
15 | 3. Load components only when needed
16 | 
17 | ## 📋 MAIN QA ENTRY POINT
18 | 
19 | When user types "VAN QA", load the main entry point:
20 | 
21 | ```
22 | fetch_rules with "isolation_rules/visual-maps/van-qa-main"
23 | ```
24 | 
25 | ## 📋 VALIDATION CHECKS
26 | 
27 | Load these components sequentially during validation:
28 | 
29 | ```
30 | 1. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/dependency-check"
31 | 2. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/config-check"
32 | 3. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/environment-check"
33 | 4. fetch_rules with "isolation_rules/visual-maps/van-qa-checks/build-test"
34 | ```
35 | 
36 | ## 📋 UTILITY COMPONENTS
37 | 
38 | Load these when needed based on validation results:
39 | 
40 | ```
41 | - For reports: fetch_rules with "isolation_rules/visual-maps/van-qa-utils/reports"
42 | - For fixes: fetch_rules with "isolation_rules/visual-maps/van-qa-utils/common-fixes"
43 | - For transitions: fetch_rules with "isolation_rules/visual-maps/van-qa-utils/mode-transitions"
44 | ```
45 | 
46 | ## ⚠️ CRITICAL REMINDERS
47 | 
48 | Remember to call these rules at these specific points:
49 | - ALWAYS load the main QA entry point when "VAN QA" is typed
50 | - ALWAYS load dependency-check before starting validation
51 | - ALWAYS load reports after completing validation
52 | - ALWAYS load mode-transitions after successful validation
53 | - ALWAYS load common-fixes after failed validation
54 | 
55 | ## 🔄 FULL VALIDATION SEQUENCE
56 | 
57 | Complete sequence for a QA validation process:
58 | 
59 | 1. Load main entry: `isolation_rules/visual-maps/van-qa-main`
60 | 2. Load first check: `isolation_rules/visual-maps/van-qa-checks/dependency-check`
61 | 3. Load second check: `isolation_rules/visual-maps/van-qa-checks/config-check`
62 | 4. Load third check: `isolation_rules/visual-maps/van-qa-checks/environment-check`
63 | 5. Load fourth check: `isolation_rules/visual-maps/van-qa-checks/build-test`
64 | 6. If pass, load: `isolation_rules/visual-maps/van-qa-utils/reports`
65 | 7. If pass, load: `isolation_rules/visual-maps/van-qa-utils/mode-transitions` 
66 | 8. If fail, load: `isolation_rules/visual-maps/van-qa-utils/common-fixes` 


--------------------------------------------------------------------------------
/isolation_rules/visual-maps/van_mode_split/van-qa-utils/rule-calling-help.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Utility for remembering how to call VAN QA rules
 3 | globs: van-qa-utils/rule-calling-help.mdc
 4 | alwaysApply: false
 5 | ---
 6 | # VAN QA: HOW TO CALL RULES
 7 | 
 8 | > **TL;DR:** This file provides examples and reminders on how to properly call VAN QA rules using the fetch_rules tool.
 9 | 
10 | ## 🚨 RULE CALLING SYNTAX
11 | 
12 | Always use the `fetch_rules` tool with the correct syntax:
13 | 
14 | ```
15 | <function_calls>
16 | <invoke name="fetch_rules">
17 | <parameter name="rule_names">["isolation_rules/visual-maps/rule-name"]
18 | </invoke>
19 | </function_calls> 


--------------------------------------------------------------------------------
/self_improve.mdc:
--------------------------------------------------------------------------------
 1 | ---
 2 | description: Guidelines for continuously improving Cursor rules based on emerging code patterns and best practices.
 3 | globs: **/*
 4 | alwaysApply: true
 5 | ---
 6 | 
 7 | - **Rule Improvement Triggers:**
 8 |   - New code patterns not covered by existing rules
 9 |   - Repeated similar implementations across files
10 |   - Common error patterns that could be prevented
11 |   - New libraries or tools being used consistently
12 |   - Emerging best practices in the codebase
13 | 
14 | - **Analysis Process:**
15 |   - Compare new code with existing rules
16 |   - Identify patterns that should be standardized
17 |   - Look for references to external documentation
18 |   - Check for consistent error handling patterns
19 |   - Monitor test patterns and coverage
20 | 
21 | - **Rule Updates:**
22 |   - **Add New Rules When:**
23 |     - A new technology/pattern is used in 3+ files
24 |     - Common bugs could be prevented by a rule
25 |     - Code reviews repeatedly mention the same feedback
26 |     - New security or performance patterns emerge
27 | 
28 |   - **Modify Existing Rules When:**
29 |     - Better examples exist in the codebase
30 |     - Additional edge cases are discovered
31 |     - Related rules have been updated
32 |     - Implementation details have changed
33 | 
34 | - **Example Pattern Recognition:**
35 |   ```typescript
36 |   // If you see repeated patterns like:
37 |   const data = await prisma.user.findMany({
38 |     select: { id: true, email: true },
39 |     where: { status: 'ACTIVE' }
40 |   });
41 |   
42 |   // Consider adding to [prisma.mdc](mdc:.cursor/rules/prisma.mdc):
43 |   // - Standard select fields
44 |   // - Common where conditions
45 |   // - Performance optimization patterns
46 |   ```
47 | 
48 | - **Rule Quality Checks:**
49 |   - Rules should be actionable and specific
50 |   - Examples should come from actual code
51 |   - References should be up to date
52 |   - Patterns should be consistently enforced
53 | 
54 | - **Continuous Improvement:**
55 |   - Monitor code review comments
56 |   - Track common development questions
57 |   - Update rules after major refactors
58 |   - Add links to relevant documentation
59 |   - Cross-reference related rules
60 | 
61 | - **Rule Deprecation:**
62 |   - Mark outdated patterns as deprecated
63 |   - Remove rules that no longer apply
64 |   - Update references to deprecated rules
65 |   - Document migration paths for old patterns
66 | 
67 | - **Documentation Updates:**
68 |   - Keep examples synchronized with code
69 |   - Update references to external docs
70 |   - Maintain links between related rules
71 |   - Document breaking changes
72 | 
73 | Follow [cursor_rules.mdc](mdc:.cursor/rules/cursor_rules.mdc) for proper rule formatting and structure.


--------------------------------------------------------------------------------

