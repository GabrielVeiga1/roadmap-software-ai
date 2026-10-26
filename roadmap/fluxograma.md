# Fluxograma do roadmap

[← Voltar ao roadmap](README.md)

Os diagramas abaixo são desenhados automaticamente pelo GitHub (e pelo Obsidian) a partir do código Mermaid. Se algum não aparecer, cole o código em [mermaid.live](https://mermaid.live) para visualizar.

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

## Por fase

### Fase 0: Fundamentos

```mermaid
flowchart LR
    A["Terminal e Linux"]
    B["Git e processos"]
    C["Redes"]
    D["Sistema operacional<br/>e concorrência"]
    A --> B --> C --> D --> E(["Entrega: repo com script bash,<br/>serviço e README em inglês"])
    classDef entrega fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class E entrega
```

### Fase 1: Engenharia de software

```mermaid
flowchart LR
    A["Python avançado"]
    B["Estruturas de dados<br/>e algoritmos"]
    C["Design de código<br/>e arquitetura"]
    D["Testes e APIs"]
    E1["SQL, Postgres<br/>e Redis"]
    F["Docker e CI"]
    A --> B --> C --> D --> E1 --> F --> E(["Entrega: API FastAPI com Postgres,<br/>Redis, Docker, testes e CI"])
    classDef entrega fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class E entrega
```

### Fase 2: Sistemas distribuídos

```mermaid
flowchart LR
    A["Escala, cache e<br/>dados distribuídos"]
    B["Filas e resiliência"]
    C["Arquitetura na prática"]
    A --> B --> C --> E(["Entrega: API + worker + fila<br/>com retry, DLQ e idempotência"])
    classDef entrega fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class E entrega
```

### Fase 3: Observabilidade

```mermaid
flowchart LR
    A["Conceitos e<br/>OpenTelemetry"]
    B["Métricas, Prometheus,<br/>Grafana e alertas"]
    C["Traces, logs<br/>e Ollama"]
    A --> B --> C --> E(["Entrega: stack de observabilidade<br/>com Collector, Prometheus, Grafana,<br/>Tempo e Loki"])
    classDef entrega fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class E entrega
```

### Fase 4: ML e LLMs

```mermaid
flowchart LR
    A["Matemática mínima"]
    B["ML e redes neurais"]
    C["PyTorch, embeddings<br/>e Transformer"]
    D["Do pré-treino<br/>ao Ollama"]
    A --> B --> C --> D --> E(["Entrega: mini-GPT treinado<br/>e README sobre atenção"])
    classDef entrega fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class E entrega
```

### Fase 5: Engenharia de IA

```mermaid
flowchart LR
    A["Prompting, tool use<br/>e RAG básico"]
    B["RAG avançado,<br/>agentes e MCP"]
    C["Evals e observabilidade<br/>de LLM"]
    D["Projeto integrador"]
    A --> B --> C --> D --> E(["Entrega: agente com Ollama + RAG,<br/>traces, evals no CI"])
    classDef entrega fill:#e6f4ea,stroke:#4a8f5f,color:#1a1a1a
    class E entrega
```

## Arquitetura do projeto final

Como as peças das Fases 1 a 5 se encaixam no agente com RAG e Ollama.

```mermaid
flowchart LR
    U(["Usuário"]) --> API["API FastAPI"]
    API --> AG["Agente"]
    API --> Q["Fila e worker"]
    AG --> LLM["Ollama<br/>modelo local"]
    AG --> RAG["RAG<br/>pgvector"]
    AG --> MCP["Tools via MCP"]

    subgraph TEL["Telemetria"]
        OTEL["OpenTelemetry<br/>Collector"]
        PROM["Prometheus"]
        TEMPO["Tempo"]
        LOKI["Loki"]
        LF["Langfuse<br/>ou Phoenix"]
        GRAF["Grafana"]
    end

    API -.-> OTEL
    AG -.-> OTEL
    Q -.-> OTEL
    OTEL --> PROM
    OTEL --> TEMPO
    OTEL --> LOKI
    OTEL --> LF
    PROM --> GRAF
    TEMPO --> GRAF
    LOKI --> GRAF

    CI["GitHub Actions<br/>testes e evals"] -. "roda evals" .-> AG

    classDef app fill:#e8f0fe,stroke:#4a6fa5,color:#1a1a1a
    classDef obs fill:#fff4e5,stroke:#c77d1a,color:#1a1a1a
    class API,AG,Q,LLM,RAG,MCP app
    class OTEL,PROM,TEMPO,LOKI,LF,GRAF obs
```
