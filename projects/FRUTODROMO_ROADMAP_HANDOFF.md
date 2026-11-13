# Frutódromo — retomada do roadmap do Claude

Data da revisão: 2026-11-13. **Planejamento apenas; nenhum arquivo do jogo alterado.**

## Evidência do ponto de parada
- Commit mais recente observado: `5cf0d731dca34d5c631ec1ca3a2493d0738e5c26` — "Etapa 6A: personagens com corpo, roupas, 5 expressões e respiração".
- Commit anterior `737b3859f0a4e625bd03f426df0dfd71a7a2ab63`: "Roadmap: etapa 5 concluída, etapa 6A em andamento".
- Commit `aef761ed3a22c5a4a8bb20480f19d3343e0c296a`: "Roadmap: etapa 5 no ar, etapa 6 em planejamento".
- Não foi encontrado roadmap nos caminhos `ROADMAP.md`, `roadmap.md`, `docs/ROADMAP.md`, `docs/roadmap.md`, `PLANO.md`, `docs/PLANO.md` ou `ROADMAP.txt`. A busca de código não retornou resultados; isso **não prova ausência de roadmap**.
- Próxima etapa **não confirmada**; não chamar 6B de etapa oficial sem documento.

## Frentes especializadas — rodada 0 (recuperação)
**Coordenador:** localizar o arquivo real do roadmap no repositório, ou solicitar ao proprietário o plano da sessão Claude. Confirmar HEAD antes de qualquer implementação.

**Engenharia:** inspecionar mudanças da 6A e dependências das próximas etapas, em trechos específicos de `js/game.js`, `css/style.css` e `index.html`; não editar.

**Arte/UX:** montar checklist de expressão, legibilidade em mobile, redução de movimento, responsividade e consistência de personagens. Não propor redesenho fora do roadmap.

**Game design:** identificar se expressões e feedback afetam compreensão dos pedidos e se existem dependências com próximas etapas.

**QA:** plano de teste para cinco expressões, troca de estado, animações, cache, saves antigos, PT/EN, janela baixa e desktop. Testes ainda não executados.

**Publicação/métricas:** verificar requisitos de portal e impactos de desempenho antes de aprovar qualquer alteração.

## Gate de execução
1. Recuperar roadmap exato.
2. Escolher próxima tarefa com base nele.
3. Definir alterações e critérios de aceite.
4. Obter autorização para modificar o jogo.
5. Implementar, revisar e testar; registrar evidências.

## Nota de consumo
Consultar `projects/FRUTODROMO_STATUS.md` e este documento antes de abrir arquivos grandes; ler apenas funções relevantes. Uma tarefa por rodada.
