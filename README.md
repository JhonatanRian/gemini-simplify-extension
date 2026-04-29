<div align="center">
  <img src="assets/logo.png" alt="Gemini Simplify Logo" width="250"/>
</div>

# Gemini Simplify Extension

An elite, polyglot software architect extension for the Gemini CLI. The `/simplify` command fuses **real-time documentation research** with **unbreakable engineering heuristics** to refactor your code to the absolute state-of-the-art.

## Installation

```bash
gemini extensions install https://github.com/JhonatanRian/gemini-simplify-extension
```

## How it Works

Unlike traditional LLM tools that guess refactoring patterns based on outdated training data, **Gemini Simplify** operates using a rigorous, language-agnostic 3-Phase Architecture:

### 1. Ecosystem Mapping (Zero-Configuration)
It silently scans your manifests and lockfiles (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, etc.) to pinpoint the exact language and framework versions you are using.
*(**Enterprise Ready:** If a `context7` MCP server is available, it gracefully detects it and loads your internal corporate architectural guidelines).*

### 2. Zero-Hallucination Research
Equipped with your exact version, it performs live web searches for the official documentation and current community best practices. It builds a ground-truth template before touching a single line of code.

### 3. Elite Parallel Orchestration
It dispatches 4 highly specialized agents concurrently to review your Git diffs. Each agent carries a rigorous software engineering checklist:

- 🏗️ **`@abstraction` (Code Reuse):** Hunts for duplicated logic, unifies copy-paste variations, and enforces native standard library usage over hand-rolled logic.
- 🧹 **`@clarity` (Code Quality):** Flattens deeply nested conditionals (ternary chains, deep switches), eradicates parameter sprawl, and removes redundant state.
- ⚡ **`@performance` (Efficiency):** Detects N+1 queries, missed concurrency, hot-path bloat, memory leaks, and recurring no-op updates.
- 🛡️ **`@standards` (The Modernizer):** Enforces strict type safety and injects the absolute state-of-the-art idioms for the exact version detected in Phase 1.

---
Made with ❤️ for the Gemini CLI community.
