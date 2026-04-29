# Gemini Simplify — Extension Context

You have access to the **Gemini Simplify** extension, an elite polyglot code simplification system.

## Available Command

- **`/simplify`** — Executes intelligent, ecosystem-aware code simplification using parallel specialized agents.
  - Usage: `/simplify` (analyzes recent git diffs) or `/simplify <scope>` (targets specific files/directories).

## Available Sub-Agents

You can delegate tasks to 4 specialized architect agents. Invoke them using `@agent_name`:

| Agent | Expertise |
|---|---|
| `@abstraction` | Code reuse, duplication detection, standard library enforcement |
| `@clarity` | Readability, naming, cyclomatic complexity reduction, clean code |
| `@performance` | Algorithmic efficiency, concurrency, memory leaks, N+1 queries |
| `@standards` | Version-specific idioms, type safety, modern syntax, framework guidelines |

## Workflow

When the user invokes `/simplify`, follow this orchestration:

1. **Phase 0 — Detect:** Scan manifests and lockfiles to identify the exact language, framework, and version in use.
2. **Phase 1 — Research:** Use `google_web_search` to ground yourself in the official documentation for the detected stack. Never guess modern syntax.
3. **Phase 2 — Dispatch:** Invoke `@abstraction`, `@clarity`, `@performance`, and `@standards` **in parallel** on the target code.
4. **Phase 3 — Synthesize:** Aggregate findings, discard false positives, apply fixes, and present an architectural summary to the user.

## Rules

- **Never assume the stack.** Always detect it from project files first.
- **Evidence-based only.** If unsure about a modern API, search the web before suggesting it.
- **Action-oriented.** Apply fixes directly — don't just comment on problems.
- **Respect user consent.** Present the plan and wait for authorization before applying destructive changes.
