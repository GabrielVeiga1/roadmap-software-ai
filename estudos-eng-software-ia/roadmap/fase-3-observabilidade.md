# Fase 3: Observabilidade

[← Voltar ao roadmap](README.md)

**Entrega da fase:** um `docker compose` com OpenTelemetry Collector, Prometheus, Grafana, Tempo e Loki observando a API, o worker e as chamadas ao Ollama.

## Conceitos e OpenTelemetry

- [ ] Logs vs métricas vs traces
- [ ] Logs estruturados e correlation ID
- [ ] Traces, spans e propagação de contexto (W3C Trace Context)
- [ ] OpenTelemetry (API, SDK, semantic conventions)
- [ ] Instrumentação automática em Python
- [ ] OpenTelemetry Collector e OTLP

## Métricas, Prometheus, Grafana e alertas

- [ ] Tipos de métrica, percentis e cardinalidade
- [ ] Prometheus (scrape, exporters)
- [ ] PromQL
- [ ] Golden signals, RED e USE, SLI, SLO e error budget
- [ ] Dashboards no Grafana
- [ ] Alertas e alert fatigue

## Traces e logs de ponta a ponta, Ollama

- [ ] Tempo (ou Jaeger) como backend de traces
- [ ] Loki e correlação entre log e trace
- [ ] Spans manuais e propagação de contexto por fila
- [ ] Sampling, custo e retenção
- [ ] Instrumentar chamadas ao Ollama (latência, tokens por segundo)
- [ ] Game day (provocar falhas e diagnosticar pela telemetria)
- [ ] Runbook (guia de resposta a incidentes)

## Entrega

- [ ] Entrega da fase concluída (descrita no topo desta nota)
