# Frutódromo — contexto compartilhado e roadmap para Claude / ChatGPT

Atualizado: 2026-11-14. Estado de retomada atual: [FRUTODROMO_STATUS.md](FRUTODROMO_STATUS.md). Os registros abaixo preservam a evolução histórica. Repositório do jogo: https://github.com/Mendesoz/frutodromo

## Regras de colaboração
- Este arquivo documenta o estado do projeto; não autoriza alterações indiscriminadas.
- Fluxo preferido: inspecionar → planejar → aprovar → implementar em branch separada → testar → relatar → aguardar validação.
- Preservar `main` do jogo. Não fazer merge ou publicação no jogo original sem autorização.
- Não confundir verificações de código com testes reais no navegador.
- Prioridade do proprietário: frutas criativas e malucas, mas pedidos reproduzíveis e aceitos; modo dica opcional.
- O endereço de testes usado pelo proprietário é https://frutodromo.pages.dev/ . Cloudflare Pages faz deploy automático da branch de produção configurada no painel; NÃO presumir que ela foi alterada para a branch da Etapa 9.

## Linha do tempo verificável
| Etapa | Branch / commit | Alteração | Evidência / status |
| --- | --- | --- | --- |
| 6B — figurinos VIP | `stage6b-vip-costumes` · `7286c9ce730cd45723d8ac980eeb887c4a559795` | Figurinos de seis VIPs em `js/game.js` | Usuário aprovou o visual; código isolado de `main` |
| 7 — polimento visual | `stage7-visual-polish` · `260d069` (prefixo visto no deploy Cloudflare) | Sombras, interface, efeitos visuais em `css/style.css` | Usuário aprovou após testar no iPhone; prefixo do commit requer conferência se precisar SHA completo |
| 8A — feedback visual | `stage7-visual-polish` · `b74d5c` | Seleção de frutas, pedidos, contraste, mobile; CSS | Implementado, sem teste individual formal |
| 8B — reações | `stage7-visual-polish` · `28db06e` | Clientes, VIPs, brilho e recompensas; CSS | Implementado, sem teste individual formal |
| 8C — responsividade | `stage7-visual-polish` · `e3a826d` | Foco, rolagem, textos e indicadores; CSS | Implementado, sem teste individual formal |
| Correção funcional de receitas/dicas | `stage7-visual-polish` · `8f67f3a934d72eac16b2bb2840217f12658ee401` | `js/game.js`: previsões de mistura, dicas alinhadas ao alvo, modo dica em Ajustes | Usuário confirmou: “Tá funcional”; não equivale a cobertura completa de QA |
| 9 — dificuldade dinâmica | `stage9-dynamic-difficulty` · `dec8ca1c239850d6562d688a44aa0f415b6eee14` | `js/game.js`: pesos de dificuldade e ajuste conforme acertos/erros | 7 verificações estáticas passaram; testes reais e publicação ainda pendentes |

## Estado atual e decisões da Etapa 9
- Branch da Etapa 9: https://github.com/Mendesoz/frutodromo/tree/stage9-dynamic-difficulty
- Base: `stage7-visual-polish`. Não houve merge em `main`.
- Percentuais-base para categorias fáceis/médias/difíceis: níveis 1–2: 85/15/0; 3–4: 65/32/3; 5–6: 55/37/8; 7+: 45/40/15.
- Adaptação dinâmica: sequência de acertos/erros desloca até 15 pontos percentuais entre fácil e difícil. Estado salvo localmente em `frutodromo_difficulty`.
- Tempo dos clientes: mantido como estava, por decisão explícita do proprietário.
- Atenção técnica: os pesos selecionam faixas de profundidade, não garantem distribuição empírica exata de pedidos; VIPs podem forçar profundidade máxima. Erros repetidos contam por tentativa, não necessariamente por cliente. Avaliar em testes.
- `reachPool(L)` gera alvos alcançáveis; `newCust()` seleciona; `showHint()` constrói dicas; `deliver()` valida entrega; `brew()` mistura; `CFG.hints` ativa/desativa dicas.
- Não afirmar que o jogo da Cloudflare já roda a Etapa 9. Para testar no mesmo domínio, será preciso promover a branch ou integrar a alteração à branch configurada, após conferir configuração e autorização de publicação.

## Pendências / QA
1. Verificar sintaxe e execução real do jogo em Safari/PWA; testar vários níveis, clientes VIP, pedidos de espécies novas e dicas ligadas/desligadas.
2. Validar que todas as receitas sugeridas são de fato reproduzíveis e aceitas, inclusive variações aleatórias e pedidos raros.
3. Medir distribuição de pedidos por nível e adaptação após sequências de erros/acertos; confirmar se o equilíbrio é divertido.
4. Registrar evidências dos testes, bugs e correções, com commits e arquivos; não marcar como concluído sem teste.
5. Preparar auditoria histórica de todas as etapas do projeto. As etapas anteriores à 6B ainda exigem levantamento de commits, não inventar histórico.
6. Não alterar a branch principal do jogo sem aprovação. O usuário quer um link único de testes, sem configuração manual repetida.

## Atualização Claude — 14/11/2026 (interface, tutorial, visual e QA)
Branch: `qa-claude-frutodromo` (base `stage9-dynamic-difficulty`), PR https://github.com/Mendesoz/frutodromo/pull/24. Não houve merge na `main` nem publicação feita pelo Claude.

**Decisões do Eric (14/11):** jogo de navegador; celular em pé. A paisagem só no contexto do CrazyGames. iPhone e PWA offline depois do lançamento. A divisão de tarefas para reenviar ao CrazyGames está aprovada em `TAREFAS_CRAZYGAMES.md` (na branch). Balanceamento, integração e publicação continuam com o Eric.

**Feito pelo Claude, com testes reais no Chromium e no WebKitGTK** (o iPhone só conta pelo relato do Eric):
| Commit | Item |
|---|---|
| `fe9a9f0` | SW registra em qualquer https (antes só em github.io); cache v44, depois v45 |
| `c990b92` | Área de toque de 40 px em telas largas de toque |
| `1a616bf` | Inglês: feira sem palavras partidas |
| `667a801` | Bug M-08: segunda entrega ao mesmo cliente pagava de novo (corrigido em memória, sem mudar o save) |
| `ca778fd` | Inglês: textos do modo dica |
| `10f43b7` | Sombras borradas das etapas 7/8 trocadas por degraus de pixel; volume medido (consistente, mas o jogo todo é baixo: pico −22,5 dBFS) |
| `9e67175` | Tutorial: PULAR TUTORIAL e mãozinha animada mostrando o gesto de arrastar (passos 1 e 2) |
| `d89f8e5` | M-02 a M-08 executados no navegador: receitas 100% reproduzidas, entrega real 125/125, 0 impossíveis em 80 mil, saves antigos ok |

Evidências: `QA_CLAUDE.md`, `docs/qa/2026-11-13/`, `docs/qa/2026-11-14/` e os scripts em `tools/qa/` (na branch).

**iPhone real (Eric, 14/11):** abertura, arraste e entrega, entrega errada e dica, fechar e reabrir, e visual sem o véu lilás: PASS. Zoom de toque duplo, segundo plano, desempenho de 10 min e PWA offline na v44 ficam para depois do lançamento.

**Para o Eric decidir (Codex implementa se aprovado):**
- LOG-01: do nível 5 em diante não há pedido de profundidade 2.
- LOG-02: o VIP não pede receita mais funda.
- LOG-03: um acerto depois de um erro zera o `streak`.
- LOG-06: nos níveis 3–6 com `streak` negativo o peso difícil fica negativo e o médio cai.
- LOG-04: o `DIFF` é por aparelho.
- Áudio: decidir se sobe o volume geral.

**Produção (verificado em 14/11, 08h40):** `frutodromo.pages.dev` serve SW v44 com a etapa 9, mas sem as correções de 14/11. Ela **não** está mais na etapa 7. Conferir no Cloudflare qual branch está publicada.

**Próximos passos do Claude:** tarefa 7, capas e vídeo novos para o CrazyGames. Depois da integração feita pelo Codex, tarefa 9: regressão final e zip do portal.
**Próximos passos do Codex:** tarefas 2 (texto da página), 3 (LOGs com o Eric) e 8 (rebase, integração).

## Ponto de recuperação
`checkpoint-stage8-visual` preserva a versão visual anterior à correção funcional de receitas.

## Links
- Jogo principal (não modificar sem autorização): https://mendesoz.github.io/frutodromo/
- Versão de testes: https://frutodromo.pages.dev/
- Etapa 9, código: https://github.com/Mendesoz/frutodromo/commit/dec8ca1c239850d6562d688a44aa0f415b6eee14

Este documento é um handoff verificável, não substitui inspeção do código nem teste real.
