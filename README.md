# Gemini Simplify Extension

<div align="center">
  <img src="assets/cli.gif" alt="Gemini Simplify CLI Demo" width="100%"/>
</div>

Automated code simplification for the Gemini CLI. The `/simplify` command combines **version-aware documentation research** with **multi-agent orchestration** to refactor code based on current best practices.

## Installation

```bash
gemini extensions install https://github.com/JhonatanRian/gemini-simplify-extension
```

## How it Works

Gemini Simplify reduces refactoring hallucinations by grounding its analysis in your project's specific environment through a 3-phase workflow:

### 1. Environment Detection
It scans manifests and lockfiles (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, etc.) to identify the exact language and framework versions in use. 

### 2. Grounded Research
Using the detected versions, it performs targeted searches for official documentation and modern idioms. This ensures suggestions are compatible with your specific stack rather than relying on generic model training data.

### 3. Parallel Agent Orchestration
It dispatches four specialized agents to analyze Git diffs or files, applying specific engineering constraints:

- 🏗️ **`@abstraction`:** Identifies duplicated logic and enforces native standard library features.
- 🧹 **`@clarity`:** Simplifies nested conditionals, reduces cyclomatic complexity, and improves naming.
- ⚡ **`@performance`:** Detects N+1 queries, concurrency issues, and inefficient resource management.
- 🛡️ **`@standards`:** Injects modern syntax and type-safe patterns specific to the detected version.

---
Made with ❤️ for the Gemini CLI community.
