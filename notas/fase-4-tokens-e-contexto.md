# Tokens, contexto e temperature

- **Fase:** 4

## O que é, em uma frase
O modelo não lê palavras, lê tokens, e a quantidade de tokens que cabe de uma vez (o contexto) limita o que ele consegue considerar.

## Como funciona
- **Token:** um pedaço de texto gerado por um tokenizador (como o BPE). Uma palavra pode virar um ou vários tokens. Em geral o português gasta mais tokens por palavra que o inglês.
- **Janela de contexto:** o máximo de tokens, somando o prompt e a resposta, que o modelo considera de uma vez. No Ollama isso é controlado por `num_ctx`; o valor padrão pode variar entre versões, então vale conferir na que você usa.
- **Custo do contexto:** quanto maior a janela, mais memória (o KV cache cresce) e mais lenta a geração.
- **Temperature:** reescala as probabilidades antes de sortear o próximo token. Perto de 0, o modelo escolhe quase sempre o mais provável (mais previsível); valores altos deixam as respostas mais variadas e mais sujeitas a erro.
- **top_p e top_k:** limitam o conjunto de candidatos antes do sorteio.

## Cuidados
- **Alucinação:** o modelo gera texto plausível, não necessariamente verdadeiro.
- **Contexto longo:** informação no meio de um texto muito grande tende a ser usada pior do que a do começo e do fim.

## O que me travou
_Anotar aqui depois de praticar._

## Como testei
_Anotar aqui depois de praticar._

## Referências
_Anotar aqui as fontes que usei._
