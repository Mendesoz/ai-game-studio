# Frutódromo — contexto compartilhado e roadmap para Claude / ChatGPT

Atualizado: 2026-11-13. Repositório do jogo: https://github.com/Mendesoz/frutodromo

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

## Ponto de recuperação
`checkpoint-stage8-visual` preserva a versão visual anterior à correção funcional de receitas.

## Links
- Jogo principal (não modificar sem autorização): https://mendesoz.github.io/frutodromo/
- Versão de testes: https://frutodromo.pages.dev/
- Etapa 9, código: https://github.com/Mendesoz/frutodromo/commit/dec8ca1c239850d6562d688a44aa0f415b6eee14

Este documento é um handoff verificável, não substitui inspeção do código nem teste real.
