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
- Prévia local: `docs/online/preview-mobile/starter-farm-a.html` no checkout do Frutódromo, branch `codex/fazenda-online-base`. Estado em 19/11: arquivos locais ainda sem commit/push; o endereço temporário do túnel só funciona enquanto o PC e o processo estiverem ligados.
- Direção e critérios mais amplos: [DIRECAO_ARTE.md](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/DIRECAO_ARTE.md). Não alegar aprovação estética da cena inteira: Eric aprovou a composição e já aprovou antes o estilo do avatar.

## Próximas entregas

1. Eric avaliar a composição A e escolher uma das três casas/pátios ou pedir ajustes; a cena interativa e a prancha estão servidas numa URL temporária enquanto o PC/túnel ficam ativos.
2. Refinar visualmente a direção escolhida e formar uma família coerente de ativos antes de ampliar o mapa.
3. Levar a composição escolhida para o mapa real do cliente, preservando os dados e a caminhada; implementar espaços de expansão e edição de fazenda com critérios próprios.
4. Manter a monetização como discovery até existir modelo que explique o que o jogador paga, que valor recebe e como seriam financiados eventuais saques. Sem prometer retorno nem implementar fluxo de dinheiro real agora.
5. Ao concluir cada marco, atualizar esta ficha e a fila; preservar a versão publicada do Frutódromo.

## Evidência e limites

- Prévia local aberta e interação de caminhada observada pelo Codex em 19/11/2026; endpoints locais e de túnel temporário responderam HTTP 200. A página das três propostas também respondeu local e remotamente. Isso valida carregamento das prévias, não experiência de usuário, performance em iPhone, economia, multiplayer ou integração ao mapa de produção.
- Repositório do código: [Mendesoz/frutodromo](https://github.com/Mendesoz/frutodromo), branch de trabalho `codex/fazenda-online-base`.
- A implementação atual tem mudanças locais sem commit/push. O status desta ficha não implica merge, deploy público ou publicação.

## Histórico

- A discussão e os requisitos do projeto online antes do novo nome permanecem em [FRUTODROMO_ONLINE_EXPLORATION.md](FRUTODROMO_ONLINE_EXPLORATION.md).
- O Frutódromo original e seu lançamento ficam no arquivo histórico [FRUTODROMO_STATUS.md](FRUTODROMO_STATUS.md).
