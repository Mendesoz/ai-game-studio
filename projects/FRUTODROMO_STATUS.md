# Frutódromo — status e retomada para agentes

## Atualização mais recente — avatar da fazenda, 16/11/2026

Na branch local `codex/fazenda-online-base` (HEAD local antes dessas alterações: `dcf6c5a`), Codex integrou no cliente do piloto o atlas ilustrado aprovado para a Iara: quatro direções e três quadros de movimento, servidos em `/play/farmer-atlas.png`. Eric pediu escala próxima ao avatar pequeno da referência Pokeidle; canvas lógico ajustado de 24×40 para 16×26 (32×52 no zoom 2; 16×26 no zoom 1). A prévia de navegador foi conferida após o ajuste e conserva WASD/botões móveis. Registro técnico em `docs/online/QA_SPRITE_AVATAR_2026-11-16.md`; preview local `http://127.0.0.1:8874/farmer-browser-preview`.

Limites: revisão visual feita na cena isolada; ainda falta conferir o mapa conectado em desktop e celular. Build, CI e regressão não foram executados nesta alteração. Os demais personagens, saves, economia, API e banco não foram alterados. A implementação e a nota de QA seguem como mudanças locais não commitadas; não houve push para o repositório do jogo. Próximo passo: conferir avatar no mapa conectado em dois tamanhos e então atualizar o status do marco.

Verificação: 14/11/2026, consulta ao GitHub pelo Codex.
Prioridade do Eric: fechar o Frutódromo para o CrazyGames e preparar a fila do estúdio.
Fila: [QUEUE.md](QUEUE.md).

## Envio manual assumido pelo Eric — 14/11/2026
- Eric confirmou que outra pessoa já jogou e testou o jogo; a declaração correspondente foi preenchida.
- Login resolvido. Codex criou um rascunho Basic Launch com o HTML da candidata aprovada, engine HTML5, save pelo SDK, suporte a celular em PORTRAIT e controle de mudo pelo SDK; sem multiplayer.
- O portal não aceita ZIP nesta tela. O arquivo correto é o `index.html` extraído do pacote aprovado, 314.316 bytes; SHA-256 `447b6516fc31a88f43aab9eee0bebdfd615de5e820b2c3b336763ae62d42eb7e`.
- A prévia/QA exibiu “Something went wrong...” antes de carregar o jogo, inclusive após recarga e autenticação da sessão do site. A causa não foi determinada. Não registrar QA Tool real como aprovado.
- Eric assumiu o envio manual (“pode deixar que eu mesmo subo”). Codex interrompeu as ações de envio. Não criar outro rascunho nem reenviar automaticamente.
- O jogo permanece como rascunho; não houve confirmação de submissão, aprovação ou lançamento no CrazyGames. Capas, vídeos e textos estão prontos no pacote entregue.
- Próximo passo: Eric conclui o QA/formulário e comunica o resultado; então atualizar o estúdio com o estado efetivamente confirmado.

## Site publicado — 14/11/2026
- [PR #26](https://github.com/Mendesoz/frutodromo/pull/26) integrado em `main`: `b47570338531fe1ac7c5782bce2b17084e563296`.
- [Deploy do GitHub Pages](https://github.com/Mendesoz/frutodromo/actions/runs/43601972688): concluído com sucesso. Codex conferiu o endereço público servindo `frutodromo-v46`, a correção LOG-06 e o novo tutorial.
- Site: https://mendesoz.github.io/frutodromo/ .
- A promoção reuniu os relatórios/evidências e o zip do QA final do Claude. A única alteração adicional de execução foi o cache v45→v46, conforme a regra do repositório.
- Sintaxe, sete testes de dificuldade e fluxo de jogo nas quatro resoluções: PASS. Atualização real de cache e três reaberturas offline com progresso e fonte preservados: PASS, 14 arquivos em cache, zero erros JS.
- [Relatório adicional](https://github.com/Mendesoz/frutodromo/blob/main/QA_PUBLICATION_CODEX_2026-11-14.md).
- Zip do portal permanece igual ao testado, sem SW: 129.678 bytes; SHA-256 `3a248e560081253c7798e243c6410973b6dfacbd21f01b43eefbca102a97be0e`.
- Materiais, texto e documentos reunidos em um pacote de entrega. Não houve submissão ao CrazyGames.
- Login resolvido e envio manual assumido pelo Eric; ver atualização acima.
- Aprovação da candidata, materiais e avanço para o envio já recebida. Não pedir a mesma aprovação novamente; tratar somente novos bloqueios concretos ou exigências do painel.
- Configuração de produção do domínio Cloudflare não foi alterada nem inferida; a publicação confirmada acima é GitHub Pages.

## Fechamento verificado — 14/11/2026, após o QA final
- Claude concluiu a tarefa 9 com PASS sobre `4c6608de42cf9dd76e635d487d727ede9fb017f9`. [Relatório completo](https://github.com/Mendesoz/frutodromo/blob/qa-claude-release/QA_RELEASE_CLAUDE_2026-11-14.md), branch `qa-claude-release` em `82e8409`; o código do jogo não mudou.
- PRs [#24](https://github.com/Mendesoz/frutodromo/pull/24) e [#25](https://github.com/Mendesoz/frutodromo/pull/25) integrados na Stage 9 após a aprovação do Eric e o QA final. HEAD: `eb216fbf56e423cc986daaca7e81a8a2fa4ca52e`. Codex conferiu com Git que sua árvore é idêntica à candidata testada.
- `main` continua em `5cf0d731dca34d5c631ec1ca3a2493d0738e5c26`; não foi promovida por esta integração.
- Pacote: [frutodromo-crazygames-4c6608d.zip](https://github.com/Mendesoz/frutodromo/blob/qa-claude-release/release/frutodromo-crazygames-4c6608d.zip), 129.678 bytes, somente `index.html`.
- Codex extraiu o arquivo binário do Git e conferiu SHA-256: `3a248e560081253c7798e243c6410973b6dfacbd21f01b43eefbca102a97be0e`. Materiais aprovados e texto reunidos para entrega ao Eric.
- Ainda não houve submissão ao CrazyGames nem validação na QA Tool real do painel. Essa validação não é substituída pelos testes locais com SDK simulado.
- Na eventual promoção do site/PWA, cumprir a regra do repositório de aumentar a versão do cache; o zip do portal não usa SW.

Os registros abaixo preservam as etapas anteriores; esta atualização tem precedência para o estado atual.

## Estado observado anteriormente
- Claude: `qa-claude-frutodromo` em `0170b41626c9db2de82eeea920d73bdc6ae2752a`; [PR #24](https://github.com/Mendesoz/frutodromo/pull/24) para `stage9-dynamic-difficulty`.
- Codex: `qa-chatgpt-logic` em `3152724d6d56c51328c4517a72a51ba40b12ebde`, sincronizada anteriormente com `d89f8e5`; incorporar atualizações seguintes do Claude antes de consolidar.
- `main` do jogo em `5cf0d73`; Stage 9 em `9cf9575`. Não houve merge nem nova publicação feitos pelo Codex nesta verificação.
- A prévia do Claude foi publicada automaticamente em https://qa-claude-frutodromo.frutodromo.pages.dev/ conforme comentário do bot no PR. Isso não identifica a branch de produção do domínio principal.

## Claude: concluído conforme relatório e commits
- Correção de entrega duplicada, traduções e suporte ao SW fora de github.io.
- `10f43b7`: sombras em degraus de pixel e medição de áudio; volume geral baixo, mantido sem ajuste automático.
- `9e67175`: Pular tutorial e mãozinha animada; cache v45. O relatório registra testes de tutorial, movimento reduzido, idioma e regressão sem erros no Chromium.
- `f314d30`: capas e vídeos novos gerados com os sprites atuais: capas 1920×1080, 800×1200 e 800×800, vídeo paisagem de 20 s e retrato de 18 s, sem som. Conforme Claude, gravação sem erros; materiais aprovados pelo Eric em 14/11. Scripts em `tools/marketing/`. Atualização do patch 14b incorporada pelo Codex.
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
| Capas e vídeo atuais | Claude + Eric | Gerados em `f314d30`; aprovados pelo Eric em 14/11 |
| Candidata integrada com SHAs fixados | Codex + revisão Claude | Disponível no PR #25, SHA `4c6608de42cf9dd76e635d487d727ede9fb017f9`; sem promoção de main/stage9 |
| Regressão final, zip e QA Tool do portal | Claude + Eric | Claude confirmou início no PR #25 às 09h56 BRT; relatório final pendente |
| Aprovação da candidata, materiais e avanço para envio | Eric | Recebida em 14/11 (“Tá aprovado”); QA final continua como condição antes de publicar |

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

## Aprovação e execução da tarefa 9 — 14/11/2026
Eric respondeu “Tá aprovado” à apresentação da candidata, materiais e avanço para o envio. A aprovação foi comunicada pelo Codex à sessão do Claude pelo terminal e confirmada no PR #25. O QA final permanece obrigatório antes de qualquer publicação.

[Atualização do Claude no PR #25](https://github.com/Mendesoz/frutodromo/pull/25), às 09h56 BRT: iniciou sobre `4c6608d`, em checkout destacado, sem alterar código. Relatou aprovação em sintaxe, 7/7 testes de dificuldade, fluxo inicial, regressão em seis tamanhos, tutorial, tradução, M-08, dicas/VIP, toque/responsividade, saves antigos, receitas, LOG-06 em navegador, PWA offline 3/3, WebKit e build do portal com/sem SDK. Restavam WebKit com entrega, desempenho e sessão longa. Estes são resultados relatados pelo Claude; o Codex ainda não conferiu o relatório final nem o zip final.

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
