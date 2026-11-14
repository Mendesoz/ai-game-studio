# Claude Code — instruções enxutas

Leia `AGENTS.md` e `docs/WORKFLOW.md` antes de alterar projetos. Não presuma testes nem aprovações sem evidência.

## Memória compartilhada do estúdio
O centralizador permanente de todos os jogos é https://github.com/Mendesoz/ai-game-studio. Leia e siga `docs/COORDINATION.md`, inclusive quando trabalhar no repositório de um jogo. Antes de iniciar ou retomar, consulte a ficha e o plano atuais; ao concluir uma tarefa significativa ou receber uma decisão aprovada, atualize o centralizador com estado, próximos passos e links de commits/testes. Codex e Claude devem usar o mesmo registro, sem depender de o Eric transportar mensagens entre chats.

## Frutódromo
Plano de conclusão: `projects/FRUTODROMO_FINISH_PLAN.md`.
Contexto histórico sob demanda: `projects/FRUTODROMO.md`.
O jogo está em `Mendesoz/frutodromo`, branch de referência `stage9-dynamic-difficulty`.
Preserve `main` e o deploy; trabalhe em branch/PR próprio. Sem novas mecânicas.

## Eficiência de contexto e tokens
- Uma tarefa específica por sessão; use `/clear` entre tarefas independentes, após registrar achados/commits. Para continuar uma sessão longa, `/compact` preservando decisões, arquivos, SHAs e pendências.
- Leia apenas arquivos e trechos necessários; use busca por função e diffs. **Não carregue `js/game.js` inteiro** salvo necessidade demonstrada; ele é grande.
- Evite repetir histórico, logs longos, relatórios integrais e respostas verbosas. Reporte: achado, evidência, arquivo/linha, alteração, teste e SHA.
- Sonnet para implementação/QA habitual; Haiku para tarefas mecânicas quando disponível; Opus apenas para diagnóstico complexo. Verifique disponibilidade com `/model`.
- Use `/context` para identificar excesso de contexto. Não execute agentes paralelos ou pesquisas amplas sem ganho claro.
- Não economize tokens omitindo testes, revisão de segurança ou evidências importantes.

A documentação detalhada fica nos arquivos de projeto, não neste `CLAUDE.md` carregado a cada turno.
