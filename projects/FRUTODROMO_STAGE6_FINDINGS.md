# Frutódromo — Etapa 6: investigação aprofundada e correções propostas

**2026-11-13. Somente inspeção estática do GitHub; nenhuma edição em `Mendesoz/frutodromo`.** Base `5cf0d731dca34d5c631ec1ca3a2493d0738e5c26`.

## Evidência e achados
1. **Pendência confirmada de implementação:** `js/game.js:151` declara `const role=null; // figurinos VIP: 6B`. O código de roupas especiais (chefj, coat, blazer, suit, vest) e acessórios condicionados a `role` existe em `js/game.js:166–195`, mas não é acionado por esse seletor. **Não significa que os VIPs não tenham nenhum destaque**: há pin, etiqueta VIP e multiplicador. A etapa 6B é indicada por comentário, mas seu escopo exato não foi recuperado.
2. **Animação de entrada/saída:** `css/style.css:52–56` combina `.cust.come/.leave/.sad/.happy` com animações. Seletores `.cust.cust.leave` são válidos, embora redundantes. É necessária validação visual antes de declarar bug.
3. **Estados e paciência:** `js/game.js:328–334, 462–474, 1329–1337` usam `exOf`, `data-ex` e atualização a cada 250 ms; `js/game.js:525–533` aplica humor feliz/triste na entrega. Testar transições, saída e sobreposição de suor/fumaça em telas pequenas.
4. **Cache:** `js/game.js:322–326` guarda até 12 folhas; `newCust` pré-gera. Medir tempo em dispositivo real antes de otimizar.
5. **Movimento reduzido:** `css/style.css:287` desativa/reduz animações globalmente; não há falha comprovada sem navegador.

## Plano proposto, ainda não autorizado
**Subetapa 6B sugerida — identidade visual VIP**
- Direção de arte: propor 6 silhuetas/figurinos legíveis para Chef Estrelado, Crítica Gourmet, Cientista Maluca, Prefeito, Influencer Fit e Colecionador, preservando o estilo 40×52 e a escala 2×.
- Engenharia: usar os atributos VIP já existentes, mapear papéis apenas para desenho, sem campos novos no save; ativar os desenhos já previstos, minimizando alterações em `js/game.js`.
- QA: comparar VIPs e clientes comuns nas 5 expressões, tipos de cliente, entrada/saída, desktop, mobile, janela baixa, PT/EN, saves antigos e movimento reduzido; verificar arrastar frutas até clientes e desempenho.
- Escopo: `js/game.js` e, somente se estritamente necessário, `css/style.css`. Sem alterações em economia, geração de clientes, recompensas, pedidos, saves ou gameplay.
- Não adicionar dependências.

**Validação 6A (antes ou junto da 6B):** observar animações, alinhamento de balões, sobreposições e desempenho. Corrigir apenas defeitos reproduzidos; apresentar qualquer correção fora do mapeamento VIP antes de aplicar.

## Evidência pendente
Não foram executados testes de navegador, benchmarks nem capturas antes/depois. Não foi feita alteração no jogo. Etapa 7 bloqueada.

## Aprovação necessária
O proprietário deve aprovar **especificamente** a implementação visual da 6B (figurinos VIP) ou optar por apenas revisar 6A. Depois da implementação autorizada, produzir relatório, pedir aceite e parar.
