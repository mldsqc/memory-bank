# Meta-Rules for Instruction Maintenance

> **TL;DR:** Guidelines for creating and improving this instruction set to ensure consistency, clarity, and effectiveness.

## Rule Structure and Formatting
- **Main Points in Bold:** With sub-points for detail.
- **File References:** Use `[filename](mdc:path/to/file)`.
- **Code Examples:** Use language-specific, fenced code blocks with DO/DON'T examples.
- **Diagrams:** Use MermaidJS for workflows and structures.
- **Headers:** Use `#`, `##`, `###` for clear, hierarchical sections.

## Rule Content Guidelines
- Start with a high-level overview or a `> **TL;DR:**` summary.
- Include specific, actionable requirements.
- Keep rules DRY (Don't Repeat Yourself) by referencing `core_utilities.md` or other modes.

## Continuous Improvement Process
- **Triggers for Updates:**
    - New code patterns emerge that aren't covered.
    - Common errors could be prevented by a better rule.
    - A new library or tool is adopted.
- **Analysis Process:**
    - Identify patterns that need to be standardized.
    - Compare new code with existing rules to find gaps.
- **Rule Updates:**
    - **Add** new rules when a pattern is used in 3+ instances.
    - **Modify** existing rules when better examples are found or edge cases are discovered.
- **Deprecation:** Mark outdated patterns as deprecated and provide migration paths.