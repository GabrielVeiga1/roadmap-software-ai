# OpenTelemetry: conceitos principais

- **Fase:** 3

## O que é, em uma frase
Um padrão aberto para gerar, coletar e exportar telemetria (traces, métricas e logs), independente de qual ferramenta guarda os dados.

## Como funciona
- **Não é um backend.** Ele define as APIs, os SDKs, o protocolo (OTLP) e o Collector. Quem armazena e mostra são Tempo, Jaeger, Prometheus, Grafana etc.
- **Trace e span:** um trace é a jornada de uma requisição; cada span é uma etapa, com nome, início e fim, atributos, eventos, status e referência ao span pai.
- **Propagação de contexto:** entre serviços, o cabeçalho `traceparent` (padrão W3C Trace Context) leva o trace id e o span id. Em filas, a mesma informação precisa ir junto nos headers da mensagem, senão o trace quebra.
- **Instrumentação:** automática (bibliotecas conhecidas, como FastAPI e SQLAlchemy) ou manual (spans que você cria para a sua lógica).
- **Collector:** recebe dados (receivers), trata (processors) e envia (exporters). Assim a aplicação não fica acoplada ao backend.
- **Semantic conventions:** nomes padronizados de atributos, para que ferramentas diferentes entendam os mesmos dados.

## Aplicação em LLMs
Dá para criar um span para cada chamada ao modelo, com atributos como modelo, tokens de entrada e saída e latência. Assim a chamada ao Ollama aparece no mesmo trace da requisição da API.

## O que me travou
_Anotar aqui depois de praticar._

## Como testei
_Anotar aqui depois de praticar._

## Referências
_Anotar aqui as fontes que usei._
