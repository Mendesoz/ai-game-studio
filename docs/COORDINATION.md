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
