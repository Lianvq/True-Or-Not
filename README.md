# True Or Not

Projeto final da disciplina de Introdução a Algoritmos/Programação, desenvolvido com Python e Pygame.
Tema: **Inteligência Artificial no Cotidiano: Aplicações e Uso Responsável**.

## Integrantes do grupo

- Lian Vasconcelos Queiroz

## Estrutura do projeto

- `main.py`: ponto de entrada da aplicação.
- `src/`: código-fonte principal do jogo.
  - `regras.py`: lógica do jogo sem Pygame (criar item, dica do assistente, colisão, pontuação, estado da partida, recorde).
  - `jogo.py`: loop principal, movimento e desenho na tela.
- `assets/`: imagens, fontes e sons.
- `data/`: arquivos persistentes (`itens.json` com os itens do jogo e `recorde.txt` com o recorde).
- `tests/`: testes unitários com `pytest`.
- `docs/`: documentação do projeto, incluindo proposta inicial.

## Descrição do jogo

Itens caem do topo da tela e o jogador controla uma cesta para pegá-los. Cada item é um conteúdo (foto, notícia, vídeo ou áudio) que pode ser **real** ou **falso/gerado por IA**. Junto de cada item aparece a dica de um assistente de IA, como "IA: 92% real". Só que o assistente erra em cerca de 25% das vezes, mesmo mostrando uma confiança alta. O jogador precisa analisar os sinais descritos no item (fonte, data, sombras, mãos, voz) e decidir se confia ou não na IA.

O jogo trabalha **confiabilidade, análise crítica e conteúdos reais versus artificiais**: a IA é uma ajuda, mas o resultado precisa ser conferido por uma pessoa.

## Objetivo do jogador

Chegar a 10 pontos coletando conteúdos reais e evitando os falsos, antes de perder as 3 vidas.

## Regras do jogo

- O jogador move a cesta com as setas do teclado.
- Pegar um item real dá +1 ponto.
- Pegar um item falso tira 1 vida.
- Itens que passam sem serem pegos não alteram a pontuação.
- O assistente de IA erra em 25% das dicas, e a confiança exibida não indica se ele acertou.
- Vitória: 10 pontos. Derrota: 0 vidas.
- O maior número de pontos é salvo como recorde em `data/recorde.txt`.

## Controles

- Seta para esquerda: mover a cesta para a esquerda
- Seta para direita: mover a cesta para a direita
- ENTER: jogar novamente após o fim da partida
- ESC: sair do jogo

## Como executar o projeto

### 1. Clonar o repositório

```
git clone LINK_DO_REPOSITORIO
cd NOME_DA_PASTA
pip install -r requirements.txt
python main.py
```

## Como executar os testes

```
python -m pytest
```

## Conceitos da disciplina utilizados

Variáveis, condicionais, laços, listas (itens na tela), dicionários (estado do jogo e itens), funções, modularização (`regras.py` separado de `jogo.py`), leitura e escrita de arquivos (JSON e recorde), docstrings e testes.

## Recursos externos

- Template da disciplina: https://github.com/ICEI-PUC-Minas-PPL-CDIA/IntroAlgs_pygame_template
- Biblioteca Pygame (licença LGPL): https://www.pygame.org
- Imagens, sons e fontes: nenhum recurso externo utilizado até o momento. Se forem adicionados, listar aqui com origem e licença.

## Decisões técnicas

- A lógica do jogo fica em `src/regras.py`, sem depender do Pygame, para facilitar os testes.
- A IA do jogo é **simulada** com sorteio e uma taxa de erro; não há IA real nem serviços externos.
- Os itens ficam em `data/itens.json`, para poder ampliá-los sem mexer no código.

## Checklist mínimo para entrega

- [ ] Preencher os nomes dos integrantes.
- [ ] Preencher `LINK_DO_REPOSITORIO` e `NOME_DA_PASTA` na seção de execução.
- [x] README com nome, descrição, regras e controles do jogo.
- [x] `docs/proposta.md` com a proposta do grupo.
- [ ] Garantir que o jogo executa com `python main.py`.
- [ ] Garantir que os testes passam com `pytest`.
