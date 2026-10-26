# RAG: busca e geração

- **Fase:** 5
- **Status:** Rascunho, a revisar e reescrever com as minhas palavras
- **Origem:** rascunho conceitual escrito com apoio do Claude; as seções "O que me travou" e "Como testei" são minhas e ficam em branco até eu fazer na prática
- **Data:** _preencher_

## O que é, em uma frase
Antes de o modelo responder, você busca trechos relevantes numa base de documentos e os coloca no prompt, para a resposta se apoiar neles.

## Como funciona
- **Ingestão:** carregar os documentos, dividir em chunks, gerar o embedding de cada um e guardar num banco vetorial (como pgvector).
- **Consulta:** gerar o embedding da pergunta, buscar os k trechos mais parecidos (em geral por similaridade de cosseno), montar o prompt com eles e gerar a resposta, de preferência citando a fonte.
- **Detalhe importante:** os documentos e a pergunta precisam usar o **mesmo modelo de embeddings**.
- **Chunking:** pedaços pequenos demais perdem contexto, grandes demais diluem a informação. O overlap entre chunks reduz cortes ruins.
- **Melhorias:** busca híbrida (BM25 + vetor), reranking e reescrita da pergunta.

## Onde costuma falhar
- A busca traz o trecho errado e o modelo responde bem sobre o assunto errado.
- O modelo ignora o contexto fornecido.
- Um documento malicioso na base injeta instruções no prompt (prompt injection).
- Por isso se mede a recuperação (recall@k) e a fidelidade da resposta ao contexto, com um conjunto de perguntas de teste.

## Quando usar e quando evitar
RAG serve para conhecimento que muda ou é privado. Se o problema é o estilo ou o comportamento do modelo, fine-tuning costuma fazer mais sentido.

## O que me travou
_Preencher com a dúvida ou o erro real que apareceu._

## Como testei
_Preencher com o que rodei ou construí para ter certeza de que entendi._

## Referências
_Adicionar as fontes que eu realmente usei._
