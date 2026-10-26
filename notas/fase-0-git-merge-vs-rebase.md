# Git: merge vs rebase

- **Fase:** 0

## O que é, em uma frase
Duas formas de levar as mudanças de uma branch para outra: o `merge` junta as duas histórias, e o `rebase` reaplica os seus commits em cima de uma base nova.

## Como funciona
- **Merge:** cria um commit de merge com dois pais (a não ser que dê para só avançar a branch em linha reta, o chamado fast-forward). Os commits originais ficam intactos, então o histórico mostra o que aconteceu de verdade.
- **Rebase:** pega os commits da sua branch e os reaplica, um por um, sobre outro ponto. Como o pai de cada commit muda, eles ganham **novos hashes**: na prática, o histórico é reescrito e fica linear.
- **Conflitos:** no merge você resolve tudo de uma vez; no rebase, commit por commit (`git rebase --continue` para seguir, `git rebase --abort` para desistir).

## Quando usar e quando evitar
- Rebase na **sua** branch local para atualizá-la com a `main` antes de abrir o PR, e `git rebase -i` para limpar commits.
- Merge (ou squash merge) para integrar a branch na `main`.
- **Não faça rebase em branch que outras pessoas já puxaram.** Se você reescreveu uma branch só sua que já foi enviada, o push exige `git push --force-with-lease`, que é mais seguro que `--force`.

## O que me travou
_Anotar aqui depois de praticar._

## Como testei
_Anotar aqui depois de praticar._

## Referências
_Anotar aqui as fontes que usei._
