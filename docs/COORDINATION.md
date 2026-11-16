# Coordenação e memória compartilhada do estúdio

Decisão do Eric registrada em 14/11/2026.

## Centralizador permanente
https://github.com/Mendesoz/ai-game-studio é a referência compartilhada de Codex e Claude para o Frutódromo e os próximos jogos. Os chats servem para executar e discutir tarefas; decisões duradouras e o ponto de retomada devem ficar neste repositório.

Cada jogo mantém código, testes e evidências no próprio repositório. O centralizador mantém contexto, planejamento e links para esses registros, sem duplicar logs extensos.

## Antes de iniciar ou retomar
1. Atualizar a consulta ao centralizador e ler `AGENTS.md`, `CLAUDE.md` e `docs/WORKFLOW.md`.
2. Ler a ficha do jogo em `projects/` e o plano vigente, quando houver.
3. Conferir branches, commits e trabalho em andamento no repositório do jogo. Registros anteriores são históricos; confirmar fatos que possam ter mudado.
4. Respeitar as decisões do Eric e a divisão de responsabilidades. Documentar conflito entre instruções antigas e decisões mais recentes.

## Quando atualizar
O agente responsável deve atualizar o centralizador ao concluir uma tarefa significativa, registrar uma decisão aprovada, mudar o escopo ou preparar uma pausa ou handoff. Não depender de o Eric copiar conclusões entre chats.

Registrar de forma curta:
- decisão e data, distinguindo aprovação do Eric de proposta do agente;
- estado atual, responsável e próxima ação;
- repositório, branch, commit e PR relevantes;
- testes realmente executados, ambiente, resultado e link das evidências;
- pendências, limitações e decisões que ainda dependem do Eric.

Preservar o histórico e identificar o que substitui registros antigos. Conferir a versão remota antes de enviar uma atualização para preservar o trabalho do outro agente. Preferir uma alteração pequena e focada.

## Frutódromo: prioridades atuais
Decisões comunicadas pelo Eric em 14/11/2026:
- Jogo exclusivo de navegador, com suporte ao computador e ao celular em pé como orientação principal no telefone.
- Rodar bem no iPhone é um diferencial. A adaptação horizontal deve ser avaliada no contexto do CrazyGames, sem deslocar a prioridade do celular em pé.
- Codex responde por lógica, mecânicas, dificuldade, receitas, persistência e testes dessa área.
- Claude responde por interface, responsividade, desempenho e QA visual. Eric informou que Claude já está trabalhando nas conclusões sobre tutorial, visual e materiais do CrazyGames; conferir seu estado antes de tocar nessas áreas.
- Mudanças de balanceamento pendentes continuam dependendo de decisão do Eric. Registrar hipóteses e medições sem alterar regras silenciosamente.
- Integração e publicação do jogo continuam sujeitas à autorização do Eric.

Referências: [ficha do projeto](../projects/FRUTODROMO.md), [plano de conclusão](../projects/FRUTODROMO_FINISH_PLAN.md) e [repositório do jogo](https://github.com/Mendesoz/frutodromo).

## Comunicação entre agentes
O registro no GitHub é persistente, mas não injeta mensagens automaticamente em conversas já abertas. Ao transmitir uma atualização, indicar o documento e o commit. Diferenciar mensagem preparada, mensagem enviada e confirmação recebida. Não afirmar que a ponte entre chats está ativa sem testar.

## Trabalho em segundo plano
Preferência operacional do Eric, 14/11/2026: enviar as tarefas em um único chat e continuar usando o computador normalmente. A coordenação deve usar chamadas programáticas ao Claude Code e ao Codex, em processos sem janela e sem capturar mouse, teclado ou foco. Operar a interface do desktop para coordenar agentes exige um pedido explícito do Eric.

As chamadas do Claude Code usam sessões dedicadas, com o contexto do centralizador e tarefas delimitadas. Elas não recebem automaticamente o histórico nem enviam mensagens à conversa que já está aberta no aplicativo. Não confundir a sessão dedicada com a frente visual que já está em andamento; conferir responsáveis e branches antes de iniciar implementação.

**Validação realizada em 14/11/2026 pelo Codex:** uma chamada programática ao Claude Code, limitada à leitura, consultou `AGENTS.md`, `CLAUDE.md` e `docs/COORDINATION.md` e devolveu uma confirmação em português diretamente ao processo chamador. Resultado: sucesso, sem recusas de permissão; diretório de trabalho permaneceu limpo. O teste não abriu janelas nem enviou mensagens à conversa antiga. Isto valida uma troca pelo terminal; não representa um serviço permanente de fila nem sincronização dos históricos dos aplicativos.

## Confirmações de leitura
- Claude, 14/11/2026: leu `AGENTS.md`, `CLAUDE.md`, `docs/COORDINATION.md` e a ficha do Frutódromo em `c3d95c6`, e adotou a rotina. Limitação: a sessão do Claude não tem permissão de push neste repositório (o GitHub App não está instalado para ele). Enquanto não houver acesso, o Claude publica a atualização como patch na branch `qa-claude-frutodromo` do jogo (`docs/studio-sync/`) e avisa para alguém aplicar.

## Comunicação com a sessão do Claude em andamento — validada em 14/11/2026
Além do teste com uma sessão local dedicada, o Codex enviou uma mensagem de coordenação à sessão em nuvem do Claude vinculada aos commits do Frutódromo, usando o comando oficial `claude -p --cloud <session-id> --output-format json`. A resposta confirmou `ok: true`. Nenhuma interface do computador foi operada.

A mensagem entregou o PR #25 e o SHA `4c6608d` para a tarefa 9 já prevista (regressão final e zip), preservando a exigência de aprovação para merge/publicação. A confirmação de entrega não prova leitura, início ou conclusão do trabalho; acompanhar evidências no GitHub. O envio é explícito para uma sessão identificada, não uma sincronização automática de todos os chats.

## Frente de fazenda — alinhamento atual de 15/11/2026
- Referência principal de integração: [PR #29](https://github.com/Mendesoz/frutodromo/pull/29), branch `codex/fazenda-visual`, sobre o protótipo do Claude. Ler [DIRECAO_ATUAL.md](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-visual/docs/online/DIRECAO_ATUAL.md) e a ficha antes de iniciar trabalho.
- Eric pediu referência de gameplay Hay Day com identidade original, fazenda personalizável e sem caldeirão. Brotalume é nome de trabalho proposto.
- Nesta rodada Codex fez cenário/apresentação; solicitou ao Claude revisão de gameplay/economia no comentário do PR. Confirmação de aceite ainda pendente; não presumir uma resposta.
- Antes de editar a mesma área, combinar tarefa e arquivos no PR; antes de push, conferir HEAD remoto. Se a base avançar, integrar preservando ambas as contribuições, sem reescrever histórico compartilhado ou descartar o outro trabalho.
- Há registro durável compartilhado, não sincronização automática de conversas antigas. Distinguir mensagem publicada, entrega direta e resposta. Em 15/11, a chamada direta pelo Claude Code local falhou por autenticação expirada; o comentário no PR foi publicado, mas isso não é prova de leitura.

## Continuidade da fazenda até 30/11 — atualização de 15/11/2026
- Implementação e colaboração ampliada autorizadas. Fonte atual: [PR #30](https://github.com/Mendesoz/frutodromo/pull/30), [PLANO_NOVEMBRO.md](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/PLANO_NOVEMBRO.md) e [issue #31](https://github.com/Mendesoz/frutodromo/issues/31).
- Codex implementou banco/API/testes; Claude realmente respondeu a duas tarefas de proposta e código, sem editar. Achados integrados;18testes local/PostgreSQL17, build/auditoria/sintaxe PASS no CI43709893238, código4234e4d. Documentação final:e9a180d.
- Autenticação anterior resolvida; não há ponte com o chat antigo da extensão. Próxima divisão: Codex mapa/cliente/API; Claude revisão de fluxo/QA em tarefas/arquivos combinados. Não presumir que a sessão antiga esteja implementando a mesma área.
- Frontend ainda não conectado; sem mercado/finanças. CI e revisão sob comando automatizados; não há desenvolvimento permanente/agendado. Atualizar a ficha antes de retomar e conferir responsáveis/HEAD sem reescrever histórico compartilhado.

## Fazenda — marco de mapa fechado em16/11/2026
- Cliente e mapa ligados ao servidor no PR#30, código3d113ec e documentação17e20d3.29testes e PostgreSQL real verdes, quatro telas e falhas/troca de conta testadas na UI; ver ficha/QA.
- Codex fez cliente/estático/integração e QA; Claude implementou layout/migração/move/customize/testes em arquivos reservados e revisou a integração. Áreas desta rodada liberadas no roadmap do jogo.
- Próxima área a reservar: mercado virtual (etapa3). Combinar módulo/arquivos antes de delegar escrita; preservar transações, idempotência, razão, trava ordenada entre fazendas e main. Nenhum pagamento/saque.
- Prévia local em http://127.0.0.1:8860/play/; não anunciar backend hospedado. Testes CI automáticos por envio; sem serviço permanente de desenvolvimento.

- Reforço final do marco16/11: fazenda esperada validada no servidor antes de executar comando;29testes verdes no CI43850499270. A checagem cobre a troca de cookie em outra aba, além do descarte de pedidos na troca explícita de conta.
