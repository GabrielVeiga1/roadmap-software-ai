# Fase 2: Sistemas distribuídos e arquitetura

[← Voltar ao roadmap](README.md)

**Entrega da fase:** a API da Fase 1 evoluída para API + worker + fila, com retry, dead letter queue e idempotência, mais 3 casos de system design desenhados.

## Escala, cache e dados distribuídos

- [ ] Escalabilidade horizontal vs vertical e estimativas de capacidade
- [ ] Cache (estratégias, invalidação, stampede) e CDN
- [ ] Replicação, sharding e consistent hashing
- [ ] Teorema CAP, PACELC e consistência eventual
- [ ] Load balancing, API gateway e rate limiting
- [ ] System design de um encurtador de URL

## Filas e resiliência

- [ ] Filas vs pub/sub e dead letter queue
- [ ] Garantias de entrega e idempotência
- [ ] Kafka (conceitos)
- [ ] Timeout, retry, backoff exponencial e jitter
- [ ] Circuit breaker, bulkhead e fallback
- [ ] Outbox, saga, CQRS e event sourcing
- [ ] System design de chat ou notificações

## Arquitetura na prática

- [ ] Monolito vs microsserviços
- [ ] Comunicação síncrona vs assíncrona, event-driven e gRPC vs REST
- [ ] Workers e background jobs
- [ ] 12-factor app
- [ ] System design de rate limiter ou feed

## Entrega

- [ ] Entrega da fase concluída (descrita no topo desta nota)
