# Estudos: Engenharia de Software e de IA

Repositório onde organizo meus estudos de engenharia de software e de IA aplicada: o roadmap, as minhas anotações e os projetos de cada fase. A ideia é sair do "só escrevo prompt" para entender o que acontece por baixo, desde o terminal e o Git até observabilidade, LLMs locais, RAG e agentes.

## Visão geral

```mermaid
flowchart TD
    F0["Fase 0<br/>Fundamentos"] --> F1["Fase 1<br/>Engenharia de software"]
    F1 --> F2["Fase 2<br/>Sistemas distribuídos"]
    F2 --> F3["Fase 3<br/>Observabilidade"]
    F3 --> F4["Fase 4<br/>ML e LLMs"]
    F4 --> F5["Fase 5<br/>Engenharia de IA"]
    F1 -. "atalho: observabilidade antes" .-> F3

    F1 --> P1(["Projeto: Orders API"])
    F3 --> P2(["Projeto: Observability Stack"])
    F4 --> P3(["Projeto: Mini GPT"])
    F5 --> P4(["Projeto: Agente com RAG e Ollama"])

    classDef fase fill:#e8f0fe,stroke:#4a6fa5,color:#1a1a1a
    classDef projeto fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class F0,F1,F2,F3,F4,F5 fase
    class P1,P2,P3,P4 projeto
```

Detalhes por fase e a arquitetura do projeto final: [fluxograma completo](roadmap/fluxograma.md).

## Roadmap

O roadmap completo está em [`roadmap/`](roadmap/README.md). Atualizo o status abaixo e marco as caixinhas conforme avanço.

| Fase | Foco | Status |
| --- | --- | --- |
| [Fase 0: Fundamentos](roadmap/fase-0-fundamentos.md) | terminal, Git, redes, sistema operacional | Não iniciada |
| [Fase 1: Engenharia de software](roadmap/fase-1-engenharia-de-software.md) | Python, algoritmos, design, testes, APIs, SQL, Docker, CI | Não iniciada |
| [Fase 2: Sistemas distribuídos](roadmap/fase-2-sistemas-distribuidos.md) | escala, filas, resiliência, arquitetura | Não iniciada |
| [Fase 3: Observabilidade](roadmap/fase-3-observabilidade.md) | logs, métricas, traces, OpenTelemetry, Grafana | Não iniciada |
| [Fase 4: ML e LLMs](roadmap/fase-4-ml-e-llms.md) | matemática mínima, redes neurais, Transformers | Não iniciada |
| [Fase 5: Engenharia de IA](roadmap/fase-5-engenharia-de-ia.md) | RAG, agentes, MCP, evals, observabilidade de LLM | Não iniciada |

## Projetos

Um projeto por fase, cada um com README em inglês. Todos começam como "Planned" e o status muda quando eu realmente construo.

| Projeto | Fase | Status |
| --- | --- | --- |
| [Orders API (FastAPI)](projetos/01-api-fastapi/README.md) | 1 | Planned |
| [Observability Stack](projetos/02-observability-stack/README.md) | 3 | Planned |
| [Mini GPT](projetos/03-mini-gpt/README.md) | 4 | Planned |
| [Local Agent with RAG](projetos/04-agent-rag-ollama/README.md) | 5 | Planned |

## Notas

As notas ficam em [`notas/`](notas/README.md), uma por tema, com as minhas palavras e o que me travou de verdade.

## Ferramentas

Claude Code no desenvolvimento do dia a dia, Ollama para modelos locais e Obsidian para anotações.

---

## English summary

This repository tracks my study path in software engineering and applied AI: a phase-by-phase roadmap (Linux and Git, backend engineering, distributed systems, observability, ML fundamentals, and AI engineering with local models), my notes, and one project per phase. Project READMEs are written in English and start as templates marked "Planned"; status changes only when the work is actually done.
