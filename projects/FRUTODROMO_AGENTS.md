# Frutódromo — organização por especialidades

Data: 2026-11-13. Este documento coordena trabalho; **não altera o jogo**.

## Papéis
1. Coordenação: escolher uma tarefa, definir critérios, registrar decisão e consolidar entregas.
2. Engenharia: analisar e implementar lógica com mudanças pequenas.
3. Arte/UX: avaliar clareza, mobile, animação e acessibilidade; propor alternativas para aprovação.
4. Game design: avaliar descoberta, progressão e retenção sem pressão artificial.
5. QA: revisar riscos, executar testes possíveis e separar testes reais de inspeção estática.
6. Publicação/métricas: checar requisitos CrazyGames, SDK, privacidade e instrumentação.

Os papéis são **frentes de trabalho executadas sequencialmente pelo ChatGPT**, não agentes independentes executando em paralelo.

## Primeira rodada proposta (aguardando aprovação de escopo)
- Coordenação: verificar roadmap real e HEAD antes de iniciar.
- Game design + UX: revisar a issue #23, descoberta de espécies, reaproveitando árvore e previsão.
- Engenharia: identificar pontos mínimos de alteração, sem modificar genética nem probabilidades.
- QA: definir testes para espécie inédita, repetida, níveis, PT/EN, mobile e save antigo.
- Métricas: verificar como medir uso das dicas sem coletar dados pessoais.
- Entrega: plano pequeno, estimativa de risco, aprovação do proprietário, implementação e validação.

## Regras
- Ler `projects/FRUTODROMO_STATUS.md` primeiro.
- Não reler arquivos inteiros sem necessidade; localizar funções relevantes.
- Uma issue por rodada, sem alterações em paralelo no mesmo arquivo.
- Sem mudanças no repositório Frutódromo antes de aprovar a tarefa concreta.
- Não alegar teste em navegador sem executá-lo.
- Registrar commit, testes, pendências e próximo passo ao concluir.
