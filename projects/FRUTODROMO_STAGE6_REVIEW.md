# Frutódromo — Etapa 6: revisão estática e proposta de validação

**Data:** 2026-11-13. **Status:** aguardando aprovação do proprietário. **Nenhuma alteração em `Mendesoz/frutodromo`.**

## Base analisada
- `main`, commit `5cf0d731dca34d5c631ec1ca3a2493d0738e5c26`.
- `js/game.js`: 1402 linhas, inspecionados especificamente trechos 120–145, 315–340, 458–476, 1327–1340 e busca de referências de personagens.
- `css/style.css`: 413 linhas, inspecionados trechos 42–62, 283–292 e referências de animação.
- `index.html`: estrutura de cena e carregamento, sem alteração.
- Revisão estática apenas. Nenhum teste de navegador ou medição de desempenho foi executado.

## Resultados observados
- Folhas de sprites de 3 quadros × 5 expressões, arte 40×52 renderizada em 80×104, `image-rendering:pixelated`.
- `CH.sheet` guarda até 12 folhas; `CH.frame` gera retratos sob demanda.
- `exOf` deriva expressões de `mood`, saída e paciência; no loop de 250ms atualiza `data-ex` sem redesenhar o contador.
- CSS inclui respiração/piscada, caminhada, reação feliz, triste, bravo e sinais de paciência.
- `@media(prefers-reduced-motion:reduce)` existe e desativa/reduz animações.
- Cache/geração de sprites e animações precisam de validação real em dispositivos modestos.
- Seletores `.cust.cust.leave` são redundantes, mas válidos; não tratar como bug confirmado.
- Confirmar visualmente expressão de felicidade durante saída e ausência de sobreposição em mobile.

## Proposta de execução por especialidades — ainda sem autorização de mudança
1. **Coordenação:** restringir escopo à etapa 6, fechar critérios e pedir aprovação.
2. **Arte/UX:** inspecionar 5 expressões em humanos, animais e personagens especiais, incluindo diferenças de roupa, nitidez e legibilidade a 0,5×.
3. **Engenharia:** localizar pontos mínimos de ajuste em `js/game.js` (geração, `exOf`, `renderCounter`, loop de atualização) e `css/style.css` (sprites, estados, movimento reduzido). Sem tocar genética, economia, saves, drag/drop.
4. **Game design:** conferir feedback compreensível e sem interferir em pedidos ou tempo de paciência.
5. **QA:** testar no navegador desktop e mobile (quando ambiente disponível): estados normal/worry/angry/happy/sad, entrada/saída, humanos/não humanos, modo Zen, PT/EN, `prefers-reduced-motion`, save antigo, drag/drop, caldeirão e janela baixa. Capturar antes/depois quando houver implementação.
6. **Publicação/performance:** observar tempo de geração, responsividade e estabilidade, sem criar dependências.

## Arquivos previstos
- `js/game.js`: somente se defeito confirmado em personagem/expressão/cache.
- `css/style.css`: somente se ajuste visual/animação for necessário.
- `index.html`: não previsto.
- Nenhum arquivo de save ou mecânica deve ser alterado.

## Gate
Solicitar aprovação para **validação da etapa 6 e correções estritamente visuais que forem identificadas**, ou apresentar achados e solicitar aprovação de correções específicas antes de editar. Ao concluir, relatar mudanças, arquivos, benefícios, problemas, testes reais, riscos e aguardar aceite. **Não iniciar etapa 7.**
