# Brotalume — fazenda idle de navegador

Atualizado em 19/11/2026. **Brotalume é nome de trabalho**; Eric ainda não confirmou nome definitivo. Este é o projeto principal de jogo. Ele substitui o Frutódromo como produto em desenvolvimento. O jogo original permanece como legado publicado; CrazyGames saiu dos objetivos deste projeto.

## Direção aprovada pelo Eric

- Jogo próprio para navegador: fazenda personalizável, expansão gradual e produção idle, com intenção comercial de grande receita mensal.
- Expansão híbrida: marcos de progresso liberam terrenos; recursos/moedas do jogo ocupam o terreno. Venda direta de terrenos e demais itens por dinheiro real continua sem decisão.
- O financiamento virá dos jogadores; a hipótese de que jogadores possam obter retorno sacável faz parte da visão. Fonte dos pagamentos, compras, direitos, conversão, taxas, saque, liquidez e modelo financeiro estão por definir. O protótipo atual não recebe dinheiro nem realiza pagamentos/saques.
- Gameplay usa ideias de expansão/base de Clash of Clans e fazenda de Hay Day como referências. A direção visual é própria: fábula acolhedora em pixel art, formas orgânicas, inspirada por Stardew Valley e Don't Starve; referências não autorizam copiar ativos ou interface.
- Dispositivos-alvo: computador e celular em pé. CrazyGames não é objetivo.

## Visual e mapa

- Eric escolheu a composição **A — pátio central**: casa como marco, circuito de caminhos, cultivo e animais próximos, clareira ao sul para crescer. A escolha da composição não aprova toda a arte nem define como o terreno será desbloqueado ou comprado.
- Em 19/11, Codex transformou o conceito em uma cena navegável isolada no browser: canvas 192×340, casa, pátio, dois canteiros, galinheiro, árvores e espaço de expansão; caminhada por toque/clique, WASD, setas e controles móveis; bloqueios simples em objetos.
- A cena reaproveita os assets do renderer local do Frutódromo; ainda é protótipo, sem economia, salvamento, construção/edição de layout ou progressão. Não equivale à integração do mapa no jogo conectado.
- Em 19/11, foram geradas três propostas lado a lado para a casa e o pátio, mantendo a mesma composição: madeira/coral, pedra/musgo e reboco/terracota. A prancha está em `docs/online/visual-concepts/farmhouse-courtyard-options-2026-11-19.png`; página comparativa local `/farm-house-options`. **Eric ainda não escolheu uma delas.**
- Eric gostou da primeira direção gerada e pediu em 19/11 um protótipo realmente jogável usando a ilustração, comparado diretamente à composição desenhada por código. Codex montou `/generated-farm` com o arquivo local `docs/online/visual-concepts/farm-map-generated-v1.png`, avatar Iara sobreposto, caminhada, coleta contextual e produção temporal demonstrativa. Isto cumpre o pedido de comparação jogável; não significa que a arte foi aprovada como final.
- Na variante gerada: canteiros acumulam até8 colheitas, uma a cada8s; galinheiro acumula até4 ovos, um a cada18s. Coletar paga moedas de demonstração. Sem persistência, login, backend, valor sacável ou alteração do cenário ilustrado após a coleta. `/starter-farm-a` preserva a variante composta por código, com link entre as duas.
- Direção mais recente em 19/11: Eric quer continuar a variante **feita por código**, usando a ilustração como referência de atmosfera, sem colocar a imagem gerada como fundo do jogo. Na rota `/starter-farm-a`, Codex redesenhou os canteiros como folhosas e morangos com volume/folhas/frutos, removeu galinhas estáticas deste estudo e colocou duas galinhas que vagueiam e ciscam. Fumaça da chaminé, flores/folhas ao vento e borboletas trazem movimento ambiental. Os ativos ainda são pixel art programada e candidatos, sem aprovação estética final.
- Prévia local: `docs/online/preview-mobile/starter-farm-a.html` no checkout do Frutódromo, branch `codex/fazenda-online-base`. Estado em 19/11: arquivos locais ainda sem commit/push; o endereço temporário do túnel só funciona enquanto o PC e o processo estiverem ligados.
- Direção e critérios mais amplos: [DIRECAO_ARTE.md](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/DIRECAO_ARTE.md). Não alegar aprovação estética da cena inteira: Eric aprovou a composição e já aprovou antes o estilo do avatar.

## Próximas entregas

1. Continuar refinando o mapa desenhado por código com foco em iluminação, relevo do chão, animais e legibilidade dos canteiros; usar a cena gerada apenas como referência visual.
2. Avaliar o resultado no telefone em pé e ajustar escala/controles, depois apresentar ao Eric para decisão estética.
3. Integrar a família de ativos escolhida ao mapa real do cliente, preservando dados e caminhada; implementar expansão e edição de fazenda com critérios próprios.
4. Manter a monetização como discovery até existir modelo que explique o que o jogador paga, que valor recebe e como seriam financiados eventuais saques. Sem prometer retorno nem implementar fluxo de dinheiro real agora.
5. Ao concluir cada marco, atualizar esta ficha e a fila; preservar a versão publicada do Frutódromo.

## Evidência e limites

- Prévia local aberta e interação observada pelo Codex em 19/11/2026: variante gerada caminhou até o galinheiro, acumulou e coletou hortaliças; variante por código exibiu canteiros redesenhados e duas galinhas se movendo entre quadros. Rotas locais/remotas responderam HTTP200 após atualizações. Não houve teste em iPhone físico; não valida economia, multiplayer, persistência ou integração ao mapa de produção.
- Repositório do código: [Mendesoz/frutodromo](https://github.com/Mendesoz/frutodromo), branch de trabalho `codex/fazenda-online-base`.
- A implementação atual tem mudanças locais sem commit/push. O status desta ficha não implica merge, deploy público ou publicação.

## Histórico

- A discussão e os requisitos do projeto online antes do novo nome permanecem em [FRUTODROMO_ONLINE_EXPLORATION.md](FRUTODROMO_ONLINE_EXPLORATION.md).
- O Frutódromo original e seu lançamento ficam no arquivo histórico [FRUTODROMO_STATUS.md](FRUTODROMO_STATUS.md).
