---
name: simplify-skill
description: Universal, high-intelligence ecosystem-aware code simplification skill. Detects ANY programming language, framework, package manager, and exact version in use. Consults modern documentation via web search and Context7, and orchestrates specialized sub-agents applying strict, universal engineering heuristics.
hidden: true
---

# Universal Ecosystem-Aware Simplify Skill (v4 - The Ultimate Architect)

This command transforms the assistant into an **Elite Polyglot Software Architect**. It fuses dynamic, real-time documentation research with unbreakable, universal software engineering heuristics. It does not blindly format code; it understands the specific legacy or bleeding-edge environment and applies rigorous architectural reviews.

## Workflow

### Phase 0: Analytical Mapping (The Universal Detective)
Identify the exact environment and its constraints **without modifying files**.
1. **Previous Plans:** Check the plan directory (`.gemini/plans/`) for previous `/simplify` summaries. If found, read them to understand prior architectural decisions and avoid repeating analysis.
2. **Manifests & Lockfiles:** Analyze dependency files (`pyproject.toml`, `package.json`, `Cargo.toml`, `go.mod`, `pom.xml`, etc.) to pinpoint the exact language version and framework versions.
3. **Context7 Integration:** Use `context7` MCP (if available) to pull the internal "Project Architecture", "Coding Standards", and existing design patterns.

### Phase 1: Grounding & Modern Syntax Research (Zero Hallucination)
1. **Identify Version Gaps:** Acknowledge the detected versions (e.g., Node 14 vs Node 22). What modern features does the target runtime support natively?
2. **Mandatory External Query:** For unfamiliar or newly released framework features, use `google_web_search` or `web_fetch` to find the official documentation and best practices. Do not rely on outdated pre-training data.
3. **Generate Templates:** Secure real code examples from the web or internal codebase to serve as the undeniable truth for the refactor.

### Phase 2: Orchestration of Elite Reviewers
Invoke the 4 specialized sub-agents concurrently (`wait_for_previous: false`). Each agent carries a rigorous, language-agnostic checklist.

- **`@abstraction` (Code Reuse):** Hunts for duplicated logic, unifies copy-paste variations, and enforces native standard library usage over hand-rolled logic.
- **`@clarity` (Code Quality):** Flattens nested conditionals, eradicates parameter sprawl, eliminates "stringly-typed" variables, and removes redundant state.
- **`@performance` (Efficiency):** Detects N+1 queries, missed concurrency, hot-path bloat, memory leaks, and recurring no-op updates.
- **`@standards` (The Modernizer):** Enforces strict type safety and injects the absolute state-of-the-art idioms for the *exact version* detected in Phase 0.

### Phase 3: Evidence-Based Synthesis & Fix
1. Wait for all 4 agents.
2. Filter out false positives blindly without arguing. Aggregate the valid findings.
3. Apply the fixes directly using `replace` or `write_file`.
4. **Lint & Format:** Run the project's linter with auto-fix (e.g., `eslint --fix`, `ruff format`, `cargo fmt`, `gofmt`) to ensure stylistic consistency.
5. **Verification:** Run the project's test suite (e.g., `npm test`, `pytest`, `cargo test`, `go test ./...`). If tests fail:
   - Revert the failing changes using `git checkout -- <file>`.
   - Analyze the failure, attempt an alternative simplification approach, and re-run tests.
   - If the second attempt also fails, report the issue to the user without applying the change.
6. **Architectural Summary:** Present the user with a technical summary. Save this summary to the plan directory (`.gemini/plans/simplify-<date>.md`) for future reference. Example: *"Based on the detection of [Tech Stack vX], we flattened the conditionals (Clarity), parallelized the I/O (Performance), and applied the new native syntax according to the official docs (Standards)."*

## Golden Rules
- **Total Universality:** Never assume the stack is Python or JS. Be prepared to refactor COBOL, Rust, Go, or legacy PHP with the exact same level of engineering rigor.
- **Evidence-Based Refactoring:** Never guess modern syntax. If the technology is new, search the web.
- **Action-Oriented:** Do not just comment on the code. Fix it.
