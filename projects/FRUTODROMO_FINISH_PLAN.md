# FRUTÓDROMO — PLANO DE CONCLUSÃO E HANDOFF PARA CLAUDE
Atualizado: 2026-11-13. Meta: candidato em 4 dias de trabalho coordenado; margem até 7 dias se surgirem falhas críticas. **Estimativa, não promessa de prazo nem evidência de testes.**

## Leia primeiro
1. `AGENTS.md` e `CLAUDE.md` deste repositório.
2. `projects/FRUTODROMO.md` — contexto histórico.
3. `docs/WORKFLOW.md` — regras de produção.
4. No jogo: `ROADMAP.md` e `REGRESSION_2026-11-13.md` na branch `stage9-dynamic-difficulty`.
5. Inspecione o código real antes de propor mudanças.

## Repositórios e ambientes
- Jogo: https://github.com/Mendesoz/frutodromo
- Principal protegido: `main`, https://mendesoz.github.io/frutodromo/
- Base de trabalho mais recente: `stage9-dynamic-difficulty`, https://github.com/Mendesoz/frutodromo/tree/stage9-dynamic-difficulty
- Ambiente de testes: https://frutodromo.pages.dev/ ; **não presumir que publica a branch 9**. Confirmar configuração antes de testes nela.
- Commits recentes de correção: `27f85e7fe0bc544b96ef80df2a398b39f7592ac9` (dificuldade e contagem de erros); `df9fcfc737383eed195cfad5b10b14ff66f0b389` (relatório de regressão).
- O usuário aprovou só refinamentos daqui em diante. Não implementar novas mecânicas.

## Divisão de responsabilidade sem conflito
**Claude — responsável por QA de interface e performance:** revisar CSS, HTML, JS de interface, fluxo de toque/arraste, legibilidade, menus, modal de dicas, acessibilidade prática, Safari iPhone, PWA, layout e possíveis regressões das etapas 6B–8C. Inspecionar possíveis gargalos de DOM/renderização e bugs assíncronos. **Não modificar `js/game.js` diretamente na branch compartilhada**; se precisar, criar branch própria `qa-claude-frutodromo` a partir da branch 9, documentar achado e abrir PR com mudanças pequenas. Se não puder executar Safari, marcar explicitamente como não testado. Não mexer no código de dificuldade, pedidos e salvamento sem coordenação.
**ChatGPT — responsável por mecânicas e regressão:** receitas alcançáveis, dica vs cruzamento real, pedidos e VIPs, dificuldade dinâmica, contagem de erros, persistência, testes de invariantes e simulações. Trabalhar em branch própria derivada da 9 quando houver nova alteração, e reportar commits/PRs. Não modificar CSS ou HTML sem coordenação.
**Proprietário:** testar o link integrado no iPhone/PWA, relatar falhas, aprovar promoção de branch e publicação.

## Plano de quatro dias
**Dia 1 — inventário e bugs críticos**
- Claude: inspecionar fluxo inicial, menus, responsividade, toques, arraste e PWA; criar relatório `QA_CLAUDE.md` com severidade, reprodução, ambiente e evidências.
- ChatGPT: regressão de pedidos, cruzamentos, dicas, nível, VIPs, estado adaptativo e saves; automatizar testes possíveis.
- Critério: lista única de bugs P0/P1/P2, com responsáveis; nenhum achado sem evidência rotulado como bug confirmado.

**Dia 2 — correções isoladas**
- Claude: corrigir P0/P1 de interface em branch/PR próprios, preservar visual aprovado.
- ChatGPT: corrigir P0/P1 de lógica em branch/PR próprios, preservar saves existentes e temporizadores.
- Critério: cada PR com teste de regressão ou instruções reproduzíveis e comparação com base.

**Dia 3 — integração e balanceamento**
- Revisar PRs cruzados; integrar em branch candidata separada após aprovação da integração.
- Rodar testes automatizados, medir pedidos por níveis e verificar estabilidade dos saves.
- Testar no link de homologação **somente depois de configurar/deployar branch correta com autorização**.
- Critério: zero P0/P1 conhecidos; pendências P2 documentadas; sem regressão de etapas anteriores.

**Dia 4 — validação do proprietário**
- Roteiro iPhone: nova partida, retomada, mistura, entrega certa/errada, dica on/off, VIP, níveis avançados, saída e retorno PWA.
- Ajustar somente falhas finais; congelar código e registrar SHA candidato.
- Critério: aprovação explícita do proprietário; **não publicar `main` automaticamente**.

**Dias 5–7 (contingência):** reservar para problemas reproduzidos de Safari, salvamento, receitas ou desempenho. Não transformar contingência em nova fase de funcionalidades.

## Critérios de aceite
- Nenhum pedido impossível identificado nas amostras automatizadas e cenários manuais.
- Dicas apontam para receita que realmente satisfaz o pedido; diferenças cosméticas explicadas.
- Progressão sem saltos injustos; dificuldade medida por categoria e custo real da receita; verificar pesos 45/40/15 nos níveis avançados, excluindo/identificando VIPs.
- Erros repetidos contra um mesmo cliente não derrubam dificuldade indefinidamente.
- Salvamento/carregamento e PWA sem perda de progresso nos cenários testados.
- Interface e drag/drop utilizáveis em iPhone Safari e desktop, com evidências.
- Preservação de tempos de clientes, configurações e funcionalidades já aprovadas.
- Relatório final de QA com ambiente, passos, resultado, commit e riscos remanescentes.

## Modelo de reporte para Claude
Para cada achado: `ID | Severidade P0/P1/P2 | Arquivo/linha | Passos para reproduzir | Esperado | Observado | Evidência | Testado de fato? | Proposta | Branch/commit/PR`.
Ao concluir, atualizar `QA_CLAUDE.md` na branch de trabalho e comunicar ao proprietário o PR e o que ainda não foi testado. Nunca afirmar que um teste de Safari ocorreu se só houve inspeção estática.

## Mensagem inicial ao Claude
> Você está atuando no fechamento do Frutódromo junto ao ChatGPT. Leia AGENTS.md, CLAUDE.md, projects/FRUTODROMO.md e este plano; depois inspecione a branch stage9-dynamic-difficulty do jogo e os arquivos ROADMAP.md e REGRESSION_2026-11-13.md. Sua responsabilidade primária é regressão de interface, Safari/iPhone/PWA e performance. Trabalhe em branch própria, preserve main e a branch de homologação, documente evidências e entregue PRs pequenos. Não adicione mecânicas, não altere a dificuldade/pedidos/saves sem combinar, e não publique. Primeiro produza o inventário de riscos e um roteiro de testes executável; corrija somente problemas comprovados e documentados.

## Atualização independente do ChatGPT — 2026-11-13
- Corrigido o reinício da dificuldade adaptativa quando o jogador confirma **Novo Jogo**, commit `9cf9575e965f69c4a08b70af8febf42cb4b45927` em `stage9-dynamic-difficulty`.
- Motivação: o estado `DIFF` era persistido fora do save principal; um novo jogo herdava sequência de desempenho anterior. Agora o fluxo explícito de Novo Jogo zera o estado em memória e remove a chave local correspondente.
- Não alterar a branch principal. Ainda faltam testes reais de execução, save, PWA e regressão completa. Claude deve usar a branch mais recente como base ao iniciar e não presumir que o link Cloudflare esteja atualizado.
