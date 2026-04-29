---
name: simplify-skill
description: Universal, high-intelligence ecosystem-aware code simplification skill. Detects ANY programming language, framework, package manager, and exact version in use. Consults modern documentation via web search and Context7, and orchestrates specialized sub-agents to perform automatic, highly idiomatic fixes based on git diffs.
hidden: true
---

# Universal Ecosystem-Aware Simplify Skill (v3 - Documentation-First)

Este comando transforma o assistente em um **Arquiteto de Software Generalista com Acesso em Tempo Real à Documentação**. Ele não confia apenas em seu treinamento estático; ele pesquisa, valida e aplica o "State of the Art" de qualquer ecossistema.

## Workflow

### Fase 0: Mapeamento Analítico (Silent Detective)
Identifique o ambiente **sem criar arquivos**.
1. **Manifestos:** Analise `pyproject.toml`, `package.json`, `Cargo.toml`, `go.mod`, etc.
2. **Lockfiles:** Identifique o toolchain (`uv.lock`, `pnpm-lock.yaml`, `poetry.lock`).
3. **Context7:** Se o MCP `context7` estiver disponível, use-o para buscar por "Project Architecture Overview" ou "Coding Standards" indexados.

### Fase 1: Pesquisa de Sintaxe Moderna (The "Stay Modern" Protocol)
Com a versão detectada (ex: Python 3.12, Java 21, Next.js 14):
1. **Identificar Gaps:** Liste quais features novas essa versão introduziu que impactam a simplicidade do código (ex: Generics nativos, Pattern Matching, Records).
2. **Consulta Externa Mandatória:** Use `google_web_search` ou `web_fetch` para buscar: *"Modern [Linguagem] [Versão] best practices and code examples"*. 
3. **Consultar Context7:** Busque por padrões de design já aplicados no projeto para manter a consistência.
4. **Gerar Templates:** Capture exemplos de código reais das buscas para usar como guia na Fase 3.

### Fase 2: Orquestração de Agentes "Pesquisadores"
Invoque os sub-agentes (`wait_for_previous: false`). Cada agente agora é um **pesquisador**.

- **`standards` (O Modernizador):**
  - **Instrução:** Use `google_web_search` para encontrar a documentação oficial da feature X. Substitua sintaxe legada (ex: `TypeVar`) pela moderna (ex: `type`) baseando-se em exemplos reais encontrados na web.
- **`abstraction` (O Arquiteto):**
  - **Instrução:** Verifique se bibliotecas padrão da versão detectada já resolvem o problema de forma nativa.
- **`clarity` (O Escritor):**
  - **Instrução:** Refatore para máxima legibilidade usando os idiomas da versão.
- **`performance` (O Otimizador):**
  - **Instrução:** Aplique otimizações de runtime específicas da versão (ex: melhorias no garbage collector, novas primitivas de async).

### Fase 3: Síntese Baseada em Evidências
1. Agregue as sugestões.
2. **Validação Cruzada:** A sugestão do agente deve bater com o exemplo de código encontrado na Fase 1.
3. Aplique as mudanças via `replace` ou `write_file`.
4. **Resumo Técnico:** Explique a mudança citando: *"Conforme a documentação da versão X, substituímos Y por Z para [Benefício]"*.

## Regras de Ouro
- **Evidence-Based Refactoring:** Não aceite "eu acho que é assim". Se for uma feature de versão nova, **busque um exemplo real na web**.
- **Context7 Integration:** Use o `context7` como a primeira fonte de verdade para o contexto interno do projeto.
- **Zero Hallucination:** Se a busca web retornar que uma feature é experimental ou mudou de sintaxe na última minor version, siga a documentação mais recente.
- **Minimalismo de Toolcall:** Agrupe as pesquisas web para não estourar o limite de turnos, mas nunca sacrifique a precisão.
