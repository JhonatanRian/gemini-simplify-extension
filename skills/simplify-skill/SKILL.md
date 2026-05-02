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
Invoke the 4 specialized sub-agents concurrently (`wait_for_previous: false`).
**Crucial:** Agents must NOT modify files. They must only produce a structured analysis report (Markdown or JSON) with specific line numbers and proposed changes.

- **`@abstraction` (Code Reuse):** Hunts for duplicated logic and unified abstractions.
- **`@clarity` (Code Quality):** Identifies complexity and naming issues.
- **`@performance` (Efficiency):** Detects bottlenecks and concurrency opportunities.
- **`@standards` (The Modernizer):** Validates syntax against the exact version detected.

### Phase 3: Evidence-Based Synthesis & Fix
1. **Consolidation:** Wait for all 4 reports. Compare recommendations. If two agents suggest changes to the same block, resolve the conflict based on the priority: Standards > Performance > Clarity > Abstraction.
2. **User Authorization:** Present a single, comprehensive "Refactoring Plan" to the user. **Note:** Inform the user that they will still need to confirm individual file modifications via the system's safety gates (Policy). **Wait for explicit user approval before any file modification.**
3. **Execution:** Once authorized, apply the fixes using surgical `replace` calls.
4. **Lint & Format:** Run the project's linter (e.g., `eslint --fix`, `ruff format`).
5. **Verification:**
   - Run the project's test suite.
   - If tests fail, use `git checkout -- <file>` to revert specifically the failing files.
   - Log the failure and try a less aggressive simplification if possible.
6. **Persistence:** Save the final summary to `.gemini/plans/simplify-<date>.md`.

## Golden Rules
- **Total Universality:** Never assume the stack is Python or JS. Be prepared to refactor COBOL, Rust, Go, or legacy PHP with the exact same level of engineering rigor.
- **Evidence-Based Refactoring:** Never guess modern syntax. If the technology is new, search the web.
- **Action-Oriented:** Do not just comment on the code. Fix it.
