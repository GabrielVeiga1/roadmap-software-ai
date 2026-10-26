# Observabilidade: logs, métricas e traces

- **Fase:** 3
- **Status:** Rascunho, a revisar e reescrever com as minhas palavras
- **Origem:** rascunho conceitual escrito com apoio do Claude; as seções "O que me travou" e "Como testei" são minhas e ficam em branco até eu fazer na prática
- **Data:** _preencher_

## O que é, em uma frase
Os três tipos de sinal que um sistema emite para você entender o que está acontecendo por dentro sem precisar abrir o código.

## Como funciona
- **Logs:** eventos individuais, em texto ou JSON. Respondem "o que aconteceu nesta requisição?". Têm muito detalhe e custam caro para guardar em volume.
- **Métricas:** números agregados ao longo do tempo (contador, gauge, histograma). Respondem "está bom ou ruim, e desde quando?". São baratas e boas para dashboards e alertas, mas não dizem qual requisição falhou.
- **Traces:** o caminho de uma requisição por vários serviços, dividido em spans com duração. Respondem "onde o tempo foi gasto ou onde deu erro?".
- **Juntos:** a métrica dispara o alerta, o trace aponta o serviço ou a chamada lenta, e o log explica o motivo. O elo entre eles é o `trace_id` registrado nos logs.

## Cuidados
- **Cardinalidade:** labels com valores quase ilimitados (como `user_id`) criam uma série por valor e podem estourar o Prometheus.
- **Monitoramento vs observabilidade:** monitorar é vigiar o que você já sabe que pode quebrar; observabilidade é conseguir investigar perguntas novas sem mudar o código.

## O que me travou
_Preencher com a dúvida ou o erro real que apareceu._

## Como testei
_Preencher com o que rodei ou construí para ter certeza de que entendi._

## Referências
_Adicionar as fontes que eu realmente usei._
