# Frutódromo — status e retomada para agentes

**Verificação:** 2026-11-13 (consulta ao GitHub).  
**Origem:** [Mendesoz/frutodromo](https://github.com/Mendesoz/frutodromo), branch `main`.  
**Último commit observado:** [`5cf0d73`](https://github.com/Mendesoz/frutodromo/commit/5cf0d731dca34d5c631ec1ca3a2493d0738e5c26) — personagens com corpo, roupas, cinco expressões e respiração.  
**Escopo desta análise:** leitura de README, `index.html`, trechos de `js/game.js` e `js/i18n.js`, `tools/bundle.py`, commits recentes e issues abertas. **Nenhum teste de navegador foi executado.** Não houve alteração no repositório do jogo.

## Arquitetura confirmada

- HTML/CSS/JavaScript sem engine; `index.html` carrega `css/style.css`, `js/i18n.js` e `js/game.js`.
- Interface principal estruturada em elementos DOM; Canvas é usado para gerar sprites e molduras em pixel art. Portanto, **DOM + Canvas para arte**, não um jogo inteiramente renderizado em Canvas.
- Web Audio API para música e efeitos, `localStorage` para progresso, PWA com `manifest.json` e `sw.js`, PT/EN.
- `tools/bundle.py` empacota HTML, CSS, JS, fontes e favicon em HTML único. Os arquivos-fonte separados são a fonte de verdade.
- README documenta mecânica de cruzamento de frutas, clientes, árvore de espécies, cartas, troféus e modo Zen. Descrições de README são funcionalidades **declaradas**, não validação funcional independente.
- O código de i18n observado intercepta texto da interface para tradução; avaliar riscos de manutenção antes de reutilizar essa abordagem em outros jogos.

## Trabalho recente identificado nos commits

- [5cf0d73](https://github.com/Mendesoz/frutodromo/commit/5cf0d731dca34d5c631ec1ca3a2493d0738e5c26): personagens com corpo, roupas, expressões e animações; alterações descritas no commit, não testadas aqui.
- [2f2fa85](https://github.com/Mendesoz/frutodromo/commit/2f2fa85a7ac7068a500c05e8d183ac3996befa86): ajustes de interface, tutorial, avisos e layout em janela baixa.
- [092c95a](https://github.com/Mendesoz/frutodromo/commit/092c95af54ac83ae01eb79cc15f00dd7d06fc05b): fantasma visual para arraste de fruta fora da mesa.

## Pendências abertas encontradas

1. [#19 — painel de objetivos pessoais](https://github.com/Mendesoz/frutodromo/issues/19): objetivos opcionais e próxima descoberta.
2. [#20 — desafios opcionais](https://github.com/Mendesoz/frutodromo/issues/20): variedade sem streaks nem pressão diária.
3. [#21 — resumo do dia](https://github.com/Mendesoz/frutodromo/issues/21): progresso e sugestão para próxima sessão.
4. [#22 — analytics](https://github.com/Mendesoz/frutodromo/issues/22): mapa de eventos e retenção com privacidade.
5. [#23 — pistas de descoberta](https://github.com/Mendesoz/frutodromo/issues/23): estimular curiosidade sem revelar resultados.

**Prioridade sugerida, não decisão tomada:** primeiro definir mapa de eventos e critérios de medida (#22); depois validar oportunidades de UX com jogador real, priorizando ajustes leves (#23 e #21); só então considerar novos sistemas (#19 e #20). Evitar implementar as cinco issues em paralelo.

## Pontos a verificar antes da publicação

- Estado efetivo da integração CrazyGames SDK e conformidade com suas regras atuais.
- Funcionamento real em desktop, mobile e iframe/janela baixa; testar arraste, sobreposições, tradução e persistência.
- Fluxo de backup/importação de saves antigos.
- Política de anúncios e analytics; não inferir receita ou retenção sem dados reais.
- Licenças de fontes, assets e dependências.
- Roadmap de desenvolvimento mais recente: **não localizado no caminho `ROADMAP.md`**; procurar nome/caminho correto antes de afirmar etapa atual.

## Protocolo econômico de retomada para Claude/ChatGPT

1. Leia **este arquivo primeiro**, depois somente os arquivos relacionados à tarefa.
2. Verifique o HEAD atual; se mudou desde `5cf0d73`, examine apenas os commits novos relevantes.
3. Escolha uma issue por sessão; defina escopo, critérios de aceite e arquivos afetados antes de editar.
4. Evite reanalisar `js/game.js` integralmente em cada sessão; faça buscas por funções e trechos.
5. Após a tarefa, registre: arquivos alterados, testes realmente executados, riscos e próximo passo.
6. Não modifique o Frutódromo sem autorização explícita do proprietário. Este documento está no repositório **ai-game-studio**, não no jogo.

## Estado das evidências

**Confirmado por inspeção:** estrutura dos arquivos, tecnologias acima, texto dos commits e existência das cinco issues abertas.  
**Não verificado:** jogabilidade em navegador, qualidade visual real, desempenho, aprovação CrazyGames, dados de retenção e receita.  
**Próxima ação recomendada:** revisão focada da issue #22 e checklist de QA, sem implementar funcionalidades novas antes de decidir prioridade.
