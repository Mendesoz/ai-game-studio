# Frutódromo — status e retomada para agentes

Verificação: 14/11/2026, consulta ao GitHub pelo Codex.
Prioridade do Eric: fechar o Frutódromo para o CrazyGames e preparar a fila do estúdio.
Fila: [QUEUE.md](QUEUE.md).

## Estado observado
- Claude: `qa-claude-frutodromo` em `0170b41626c9db2de82eeea920d73bdc6ae2752a`; [PR #24](https://github.com/Mendesoz/frutodromo/pull/24) para `stage9-dynamic-difficulty`.
- Codex: `qa-chatgpt-logic` em `3152724d6d56c51328c4517a72a51ba40b12ebde`, sincronizada anteriormente com `d89f8e5`; incorporar atualizações seguintes do Claude antes de consolidar.
- `main` do jogo em `5cf0d73`; Stage 9 em `9cf9575`. Não houve merge nem nova publicação feitos pelo Codex nesta verificação.
- A prévia do Claude foi publicada automaticamente em https://qa-claude-frutodromo.frutodromo.pages.dev/ conforme comentário do bot no PR. Isso não identifica a branch de produção do domínio principal.

## Claude: concluído conforme relatório e commits
- Correção de entrega duplicada, traduções e suporte ao SW fora de github.io.
- `10f43b7`: sombras em degraus de pixel e medição de áudio; volume geral baixo, mantido sem ajuste automático.
- `9e67175`: Pular tutorial e mãozinha animada; cache v45. O relatório registra testes de tutorial, movimento reduzido, idioma e regressão sem erros no Chromium.
- `f314d30`: capas e vídeos novos gerados com os sprites atuais: capas 1920×1080, 800×1200 e 800×800, vídeo paisagem de 20 s e retrato de 18 s, sem som. Conforme Claude, gravação sem erros; materiais aguardam aprovação do Eric. Scripts em `tools/marketing/`. Atualização do patch 14b incorporada pelo Codex.
- [Tarefas e responsáveis](https://github.com/Mendesoz/frutodromo/blob/qa-claude-frutodromo/TAREFAS_CRAZYGAMES.md), [QA](https://github.com/Mendesoz/frutodromo/blob/qa-claude-frutodromo/QA_CLAUDE.md) e [handoff](https://github.com/Mendesoz/frutodromo/blob/qa-claude-frutodromo/QA_HANDOFF_CHATGPT_2026-11-14.md).
- Codex está aplicando ao centralizador o conteúdo documental do [patch do Claude](https://github.com/Mendesoz/frutodromo/tree/qa-claude-frutodromo/docs/studio-sync), preservando as instruções de execução em segundo plano. A sessão atual do Claude relatou não ter push neste centralizador.

## Decisão de balanceamento aprovada pelo Eric em 14/11
Corrigir apenas LOG-06: impedir peso negativo em `diffTier()`, mantendo a proporção dos pedidos médios quando a transferência fácil/difícil atingir o limite disponível. Implementado pelo Codex em `cd869d1`: sete testes automatizados de dificuldade passaram (três falhavam antes). Checagem de jogo em Edge/Chromium nas quatro resoluções obrigatórias passou sem erros. Sintaxe e save após recarga aprovados no escopo testado.
Manter nesta versão LOG-01 (progressão/profundidades), LOG-02 (VIP), LOG-03 (erro e acerto como eventos) e LOG-04 (DIFF por aparelho). Não migrar saves.

## Itens para o reenvio
| Item | Dono | Estado nesta verificação |
|---|---|---|
| Texto da página em português e inglês | Codex | Concluído em `4a0e50a`; aguarda candidata final do portal |
| Correção aprovada LOG-06 e regressão de lógica | Codex | Concluído em `cd869d1`; 7/7 testes e checagem de navegador aprovados |
| Capas e vídeo atuais | Claude + Eric aprova | Gerados em `f314d30`; aguardam aprovação do Eric |
| Candidata integrada com SHAs fixados | Codex + revisão Claude | Disponível no PR #25, SHA `4c6608de42cf9dd76e635d487d727ede9fb017f9`; sem promoção de main/stage9 |
| Regressão final, zip e QA Tool do portal | Claude + Eric | Tarefa 9 pronta para iniciar sobre a candidata fixada; resultado final pendente |
| Aprovação do material e do envio/publicação | Eric | Pendente |

Tentar preparar o reenvio hoje é uma meta de trabalho, não uma garantia. O CrazyGames [revê as submissões](https://docs.crazygames.com/) e separa Basic Launch e Full Launch; o [Basic Launch](https://docs.crazygames.com/resources/basic-launch-metrics/) tem avaliação de 7 a 21 dias.

No telefone a prioridade é retrato. Paisagem é relevante na janela desktop do portal. Testes extras de iPhone/PWA ficam para depois do marco CrazyGames, conforme escopo registrado pelo Claude e confirmado com as prioridades do Eric.

## Candidata para a tarefa 9
- Branch: [codex/crazygames-final-logic](https://github.com/Mendesoz/frutodromo/tree/codex/crazygames-final-logic).
- SHA: `4c6608de42cf9dd76e635d487d727ede9fb017f9`.
- [PR #25](https://github.com/Mendesoz/frutodromo/pull/25), draft contra Stage 9, aguardando QA. O GitHub indicou integração limpa; não houve merge.
- Contém as alterações do Claude até `0170b41`, inclusive capas/vídeos, os documentos de lógica anteriores, LOG-06 e o texto da página.
- Relatório: [QA_RELEASE_CODEX_2026-11-14.md](https://github.com/Mendesoz/frutodromo/blob/codex/crazygames-final-logic/QA_RELEASE_CODEX_2026-11-14.md).
- Claude pode executar a regressão e gerar o pacote dessa branch sem esperar uma promoção de `main` ou `stage9`. Qualquer nova atualização da candidata requer registrar novo SHA e validar a mudança.
- CSS, tutorial, `sw.js` e scripts de QA do Claude foram preservados. Coordenar cache na promoção final do site/PWA; isso não impede o build separado do portal.

## Como retomar
1. Consultar o HEAD remoto e os comentários mais recentes do PR #24.
2. Conferir a divisão de arquivos antes de editar; Claude mantém CSS, tutorial, SW e `tools/qa/`.
3. Trabalhar em segundo plano, sem operar a interface do computador.
4. Registrar decisões, commits e testes efetivamente executados. Não promover a `main` ou enviar ao portal sem a aprovação correspondente.

## Histórico preservado — inspeção de 13/11/2026
O texto abaixo é histórico e não representa as pendências atuais. Em conflito, usar a verificação de 14/11 acima e os documentos recentes.


**Verificação:** 2026-11-13 (consulta ao GitHub).  
**Origem:** [Mendesoz/frutodromo](https://github.com/Mendesoz/frutodromo), branch `main`.  
**Último commit observado:** [`5cf0d73`](https://github.com/Mendesoz/frutodromo/commit/5cf0d731dca34d5c631ec1ca3a2493d0738e5c26) — personagens com corpo, roupas, cinco expressões e respiração.  
**Escopo desta análise:** leitura de README, `index.html`, trechos de `js/game.js` e `js/i18n.js`, `tools/bundle.py`, commits recentes e issues abertas. **Nenhum teste de navegador foi executado.** Não houve alteração no repositório do jogo.

## Arquitetura confirmada

- HTML/CSS/JavaScript sem engine; `index.html` carrega `css/style.css`, `js/i18n.js` e `js/game.js`.
- Interface principal estruturada em elementos DOM; Canvas é usado para gerar sprites e molduras em pixel art. Portanto, **DOM + Canvas para arte**, não um jogo inteiramente renderizado em Canvas.
- Web Audio API para música e efeitos, `localStorage` para progresso, PWA com `manifest.json` e `sw.js`, PT/EN.
- `tools/bundle.py` empacota HTML, CSS, JS, fontes e favicon em HTML único. Os arquivos-fonte separados são a fonte de verdade.
- README documenta mecânica de cruzamento de frutas, clientes, árvore de espécies, cartas, troféus e modo Zen. Descrições de README são funcionalidades **declaradas**, não validação funcional independente.
- O código de i18n observado intercepta texto da interface para tradução; avaliar riscos de manutenção antes de reutilizar essa abordagem em outros jogos.

## Trabalho recente identificado nos commits

- [5cf0d73](https://github.com/Mendesoz/frutodromo/commit/5cf0d731dca34d5c631ec1ca3a2493d0738e5c26): personagens com corpo, roupas, expressões e animações; alterações descritas no commit, não testadas aqui.
- [2f2fa85](https://github.com/Mendesoz/frutodromo/commit/2f2fa85a7ac7068a500c05e8d183ac3996befa86): ajustes de interface, tutorial, avisos e layout em janela baixa.
- [092c95a](https://github.com/Mendesoz/frutodromo/commit/092c95af54ac83ae01eb79cc15f00dd7d06fc05b): fantasma visual para arraste de fruta fora da mesa.

## Pendências abertas encontradas

1. [#19 — painel de objetivos pessoais](https://github.com/Mendesoz/frutodromo/issues/19): objetivos opcionais e próxima descoberta.
2. [#20 — desafios opcionais](https://github.com/Mendesoz/frutodromo/issues/20): variedade sem streaks nem pressão diária.
3. [#21 — resumo do dia](https://github.com/Mendesoz/frutodromo/issues/21): progresso e sugestão para próxima sessão.
4. [#22 — analytics](https://github.com/Mendesoz/frutodromo/issues/22): mapa de eventos e retenção com privacidade.
5. [#23 — pistas de descoberta](https://github.com/Mendesoz/frutodromo/issues/23): estimular curiosidade sem revelar resultados.

**Prioridade sugerida, não decisão tomada:** primeiro definir mapa de eventos e critérios de medida (#22); depois validar oportunidades de UX com jogador real, priorizando ajustes leves (#23 e #21); só então considerar novos sistemas (#19 e #20). Evitar implementar as cinco issues em paralelo.

## Pontos a verificar antes da publicação

- Estado efetivo da integração CrazyGames SDK e conformidade com suas regras atuais.
- Funcionamento real em desktop, mobile e iframe/janela baixa; testar arraste, sobreposições, tradução e persistência.
- Fluxo de backup/importação de saves antigos.
- Política de anúncios e analytics; não inferir receita ou retenção sem dados reais.
- Licenças de fontes, assets e dependências.
- Roadmap de desenvolvimento mais recente: **não localizado no caminho `ROADMAP.md`**; procurar nome/caminho correto antes de afirmar etapa atual.

## Protocolo econômico de retomada para Claude/ChatGPT

1. Leia **este arquivo primeiro**, depois somente os arquivos relacionados à tarefa.
2. Verifique o HEAD atual; se mudou desde `5cf0d73`, examine apenas os commits novos relevantes.
3. Escolha uma issue por sessão; defina escopo, critérios de aceite e arquivos afetados antes de editar.
4. Evite reanalisar `js/game.js` integralmente em cada sessão; faça buscas por funções e trechos.
5. Após a tarefa, registre: arquivos alterados, testes realmente executados, riscos e próximo passo.
6. Não modifique o Frutódromo sem autorização explícita do proprietário. Este documento está no repositório **ai-game-studio**, não no jogo.

## Estado das evidências

**Confirmado por inspeção:** estrutura dos arquivos, tecnologias acima, texto dos commits e existência das cinco issues abertas.  
**Não verificado:** jogabilidade em navegador, qualidade visual real, desempenho, aprovação CrazyGames, dados de retenção e receita.  
**Próxima ação recomendada:** revisão focada da issue #22 e checklist de QA, sem implementar funcionalidades novas antes de decidir prioridade.
