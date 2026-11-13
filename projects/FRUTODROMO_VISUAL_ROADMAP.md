# Roadmap original — Reformulação visual do Frutódromo

**Fonte:** texto do planejamento fornecido pelo proprietário em 2026-11-13. **Sem autorização de implementação neste registro.**

## Metodologia
Analisar etapa atual → apresentar plano técnico e arquivos/sistemas → implementar apenas etapa autorizada → testar → relatar alterações, melhorias, problemas, testes e riscos → aguardar aprovação antes de avançar.

## Etapas
1. **Fundação visual:** grade de pixels, escala lógica, resolução, proporções das frutas, nitidez.
2. **Cenário:** chão de madeira, parede/janelas, balcões, sombras e iluminação.
3. **Caldeirão:** animação da poção, fumaça/partículas, brilho e reflexos.
4. **Decoração:** caixotes, barris, cestos, lampiões, placas, balanças e laterais.
5. **Interface:** HUD, inventário, feira/cartões, balões, botões e placas.
6. **Personagens:** sprites de clientes, expressões, roupas, respiração e reações.
7. **Game Feel:** animações ambientais, reações, iluminação dinâmica, feedback visual/sonoro.
8. **Polimento:** otimização, responsividade, regressão, desempenho e revisão visual.

## Regras inegociáveis
- Não alterar gameplay, economia, progressão, saves ou sistema de frutas.
- Não quebrar arrastar/soltar; não substituir elementos funcionais desnecessariamente.
- Não adicionar dependências sem justificativa.
- Preservar identidade, proporções e hierarquia visual; grade consistente não significa objetos do mesmo tamanho.
- Respeitar `prefers-reduced-motion` e desempenho.
- Não afirmar testes de navegador não executados.
- Não fazer commits, pushes ou mudanças fora do escopo autorizado.
- Parar após cada etapa e aguardar avaliação e autorização; se houver ajustes, concluir etapa atual antes de avançar.

## Ponto de retomada identificado
- Histórico: etapa 5 concluída conforme mensagem do commit `737b385`.
- Último commit visto: `5cf0d73` descreve **6A: personagens com corpo, roupas, cinco expressões, respiração**.
- **A conclusão da etapa 6 não está comprovada.** Próxima ação é revisar a implementação de 6A contra critérios da etapa 6, definir possíveis lacunas e apresentar plano. Não presumir uma '6B' oficial sem evidência.
- Revisão/planejamento podem prosseguir; **nenhuma alteração no jogo até autorização específica**.

## Divisão por especialidades
- Coordenação: critérios, escopo, gate de aprovação.
- Engenharia: localizar funções e arquivos afetados, plano mínimo.
- Arte/UX: direção, consistência, estados e movimento reduzido.
- Game design: proteger clareza das ações e gameplay.
- QA: testes de expressões, saves, PT/EN, arraste e mobile.
- Publicação/performance: custos de renderização e portal.

## Relatório por etapa
O que mudou; arquivos; ganhos visuais; problemas; testes realmente executados; riscos; comparativo antes/depois quando possível; decisão pendente do proprietário.
