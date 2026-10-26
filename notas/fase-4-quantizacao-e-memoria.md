# Quantização e memória de modelos locais

- **Fase:** 4
- **Status:** Rascunho, a revisar e reescrever com as minhas palavras
- **Origem:** rascunho conceitual escrito com apoio do Claude; as seções "O que me travou" e "Como testei" são minhas e ficam em branco até eu fazer na prática
- **Data:** _preencher_

## O que é, em uma frase
Guardar os pesos do modelo com menos bits por número para ele caber em menos memória e rodar mais rápido, aceitando alguma perda de qualidade.

## Como funciona
- **Conta aproximada:** memória dos pesos ≈ número de parâmetros × bytes por parâmetro. Para um modelo de 7 bilhões: cerca de 14 GB em 16 bits, 7 GB em 8 bits e 3,5 GB em 4 bits. Na prática dá um pouco mais, por causa de overhead.
- **Além dos pesos:** o KV cache cresce com o tamanho do contexto e também ocupa memória.
- **GGUF:** formato de arquivo usado pelo llama.cpp (e pelo Ollama). Nomes como `Q4_K_M` e `Q8_0` indicam o tipo de quantização.
- **Trade-off:** menos bits = menos memória e mais velocidade, com perda de qualidade que costuma ser pequena em 8 bits e mais perceptível em 4 bits ou menos, variando por modelo.
- **VRAM vs RAM:** se o modelo não cabe inteiro na placa de vídeo, parte vai para a CPU e a RAM, e a velocidade cai bastante. O comando `ollama ps` mostra o tamanho carregado e como ele está dividido entre GPU e CPU.

## Quando usar e quando evitar
Escolha a maior quantização que couber confortável no seu hardware, e compare dois níveis no mesmo conjunto de perguntas antes de decidir.

## O que me travou
_Preencher com a dúvida ou o erro real que apareceu._

## Como testei
_Preencher com o que rodei ou construí para ter certeza de que entendi._

## Referências
_Adicionar as fontes que eu realmente usei._
