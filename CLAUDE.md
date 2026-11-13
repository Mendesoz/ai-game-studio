# Claude Code — instruções enxutas

Leia `AGENTS.md` e `docs/WORKFLOW.md` antes de alterar projetos. Não presuma testes nem aprovações sem evidência.

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
