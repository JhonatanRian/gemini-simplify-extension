---
name: simplify-skill
description: Universal, high-intelligence ecosystem-aware code simplification skill. Detects ANY programming language, framework, package manager, and exact version in use. Consults modern documentation via web search and Context7, and orchestrates specialized sub-agents to perform automatic, highly idiomatic fixes based on git diffs.
hidden: true
---

# Universal Ecosystem-Aware Simplify Skill (v3 - Documentation-First)

This command transforms the assistant into a **Generalist Software Architect with Real-Time Access to Documentation**. It does not rely solely on its static training; it researches, validates, and applies the "State of the Art" of any ecosystem.

## Workflow

### Phase 0: Analytical Mapping (Silent Detective)
Identify the environment **without creating files**.
1. **Manifests:** Analyze `pyproject.toml`, `package.json`, `Cargo.toml`, `go.mod`, etc.
2. **Lockfiles:** Identify the toolchain (`uv.lock`, `pnpm-lock.yaml`, `poetry.lock`).
3. **Context7:** If the `context7` MCP is available, use it to search for indexed "Project Architecture Overview" or "Coding Standards".

### Phase 1: Modern Syntax Research (The "Stay Modern" Protocol)
With the detected version (e.g., Python 3.12, Java 21, Next.js 14):
1. **Identify Gaps:** List which new features this version introduced that impact code simplicity (e.g., native Generics, Pattern Matching, Records).
2. **Mandatory External Query:** Use `google_web_search` or `web_fetch` to search: *"Modern [Language] [Version] best practices and code examples"*. 
3. **Query Context7:** Search for design patterns already applied in the project to maintain consistency.
4. **Generate Templates:** Capture real code examples from the searches to use as a guide in Phase 3.

### Phase 2: Orchestration of "Researcher" Agents
Invoke the sub-agents (`wait_for_previous: false`). Each agent is now a **researcher**.

- **`standards` (The Modernizer):**
  - **Instruction:** Use `google_web_search` to find the official documentation of feature X. Replace legacy syntax (e.g., `TypeVar`) with modern syntax (e.g., `type`) based on real examples found on the web.
- **`abstraction` (The Architect):**
  - **Instruction:** Check if standard libraries of the detected version already solve the problem natively.
- **`clarity` (The Writer):**
  - **Instruction:** Refactor for maximum readability using the idioms of the detected version.
- **`performance` (The Optimizer):**
  - **Instruction:** Apply runtime optimizations specific to the version (e.g., garbage collector improvements, new async primitives).

### Phase 3: Evidence-Based Synthesis
1. Aggregate the suggestions.
2. **Cross-Validation:** The agent's suggestion must match the real code example found in Phase 1.
3. Apply the changes via `replace` or `write_file`.
4. **Technical Summary:** Explain the change citing: *"According to the documentation for version X, we replaced Y with Z for [Benefit]"*.

## Golden Rules
- **Evidence-Based Refactoring:** Do not accept "I think it is like this". If it is a new version feature, **search for a real example on the web**.
- **Context7 Integration:** Use `context7` as the first source of truth for the internal context of the project.
- **Zero Hallucination:** If the web search indicates that a feature is experimental or its syntax changed in the latest minor version, follow the most recent documentation.
- **Toolcall Minimalism:** Group web searches to avoid exceeding the turn limit, but never sacrifice accuracy.
