# Brotalume — fazenda idle (nome de trabalho proposto)

## Estado mais recente — 15/11/2026: Brotalume (nome proposto)
Esta seção prevalece sobre o planejamento histórico abaixo.
- Eric determinou usar **Hay Day como referência de gameplay**, mantendo a essência, pixel art e sprites do Frutódromo. Fazenda personalizável, disposição de canteiros/instalações e cadeias produtivas orientam o próximo recorte. Não copiar visual ou ativos do Hay Day.
- Eric confirmou que o caldeirão não faz sentido nesta fazenda e pediu um novo nome. Codex propôs **Brotalume**, ainda como nome de trabalho; não há confirmação de marca/domínio ou escolha definitiva.
- Claude entregou protótipo executável em `c7a5903`, depois seletor de personagens, frutas/clientes originais e save v2 em `d4e4e45`, branch `claude/fazenda-prototipo`. Isso atualiza a inspeção anterior, que só tinha documentos/simulação.
- Codex preparou `codex/fazenda-visual` e integrou a revisão mais recente do Claude, preservando as duas contribuições. HEAD: `bce33792b6090432d1f3f96c6d1889d917be8781`.
- [PR #29](https://github.com/Mendesoz/frutodromo/pull/29), draft contra `claude/fazenda-prototipo`; GitHub indicou integração limpa na conferência. Nenhum merge na main.
- [Prévia da fazenda](https://codex-fazenda-visual.frutodromo.pages.dev/prototipo-fazenda/). Cloudflare informou deploy de `bce3379` concluído; Codex confirmou HTTP 200 do HTML, CSS e módulo de arte, nome BROTALUME, save v2 e ausência de caldeirão na interface.
- Reuso efetivo: molduras, fonte, personagens e decoração originais. Exterior novo com celeiro, quitanda, cercas, vegetação e animais com volume. Caldeirão removido da eclosão, agora chocadeira/ninho.
- [Direção/coordenação](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-visual/docs/online/DIRECAO_ATUAL.md) e [QA com limites](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-visual/docs/online/QA_FAZENDA_VISUAL_2026-11-15.md).
- Primeira passagem: entrada, produção, venda, compra de animal, boost, AFK e recarga; quatro tamanhos sem rolagem horizontal ou erros JS. Após integrar d4e4e45: entrada com personagem selecionado, recarga, ovo dourado colocado na chocadeira, compra de boost, entrega/agradecimento e venda reais na UI; console sem erros capturados.
- Economia/RNG/estado/produção e offline/loop idênticos a d4e4e45; ações/compras idênticas após normalizar texto de eclosão. `fazenda_proto_v2` preservado. Save do Frutódromo publicado separado.
- Ainda não existe edição livre da disposição, cadeias produtivas completas ou operação de mercado/pagamentos nesta entrega.

### Comunicação e divisão nesta rodada
- O Eric apontou visuais concorrentes. Codex publicou [alinhamento ao Claude no PR #29](https://github.com/Mendesoz/frutodromo/pull/29#issuecomment-6893110608): Codex na apresentação; Claude na revisão de gameplay/economia. A divisão foi proposta, sem confirmação de aceite recebida.
- A tentativa de chamada adicional ao Claude Code local falhou por autenticação expirada. Não afirmar que essa chamada entregou a mensagem ou obteve resposta.
- Nenhuma ponte automática com a conversa antiga do aplicativo foi estabelecida. Usar o PR e este centralizador como fonte persistente e conferir HEAD/áreas antes de editar.
- Próximo marco: revisão conjunta do recorte Hay Day — posicionar/mover um canteiro e uma instalação, persistir layout e fechar um pequeno ciclo de produção/encomenda. É proposta ainda não implementada.

Atualização: 15/11/2026. Estado atual: fazenda idle em planejamento, com documentação e molde visual do Claude; consultar a atualização abaixo. As seções de pomar/genética são históricas.
Eric indicou https://pokeidle.io/app e perguntou se seria possível produzir algo semelhante com o Frutódromo, após destacar o mercado interno e três moedas da referência.

## Atualização conferida pelo Codex — 15/11/2026
Esta seção prevalece sobre o conceito anterior de pomar/genética. Fonte: branch [claude/online-simulacao](https://github.com/Mendesoz/frutodromo/tree/claude/online-simulacao), HEAD `8fb050e3e0b56a2a4aeb2728702fed0417668849`, oito commits após `a26b439`; [PR #27](https://github.com/Mendesoz/frutodromo/pull/27), draft e ainda aberto. Nenhum merge realizado pelo Codex nesta conferência.

### Direção do Eric registrada pelo Claude
- Fazenda idle; genética e cruzamento de frutas saem do conceito.
- Produção AFK com resumo do rendimento e cena animada.
- Três moedas, com gemas de valor real no mercado entre jogadores; boosts temporários; achados e ferramentas com classificação.
- Personalização de personagem e fazenda, nomes, decoração e proposta de fazenda exibível/visitável.
- Rankings, passe e concurso/torneio; sem necessidade de boss, ginásio ou PvP.
- Ranking de fazenda a cada três meses, com sorteio citado pelo Eric. Regras, prêmios, viabilidade e operação ainda não estão fechados.

### Propostas do Claude, ainda distintas das decisões
- Animais com raridade e atributos; vender um ovo dourado ou chocá-lo.
- Desgaste de ferramentas, aposentadoria de animais e produtos perecíveis.
- Modelos Vale/Serra/Litoral, Beleza, votos e recompensas cosméticas da temporada.
- Gemas com entrada financiada por depósitos, circulação por vendas e saída por saques; cotação, taxas, pagamentos, requisitos e conciliação ainda precisam de definição. É desenho proposto, não operação validada ou autorização de integração financeira.
- [Estrutura completa](https://github.com/Mendesoz/frutodromo/blob/claude/online-simulacao/docs/online/ESTRUTURA_REFERENCIA_2026-11-14.md).

### O que existe e limites desta conferência
- O diff contém documentos, duas imagens de referência e script Python de simulação da reprodução; nenhum código de execução da fazenda foi adicionado ao repositório nessa branch.
- A simulação de linhagens virou estudo histórico de oferta/consumo após a retirada da genética. Não mede demanda real; Codex leu o código e o relatório, sem executar novamente o Python.
- Claude registrou dois materiais visuais em artifacts privados. Codex tentou abrir o molde e encontrou exigência de login; seu conteúdo visual não foi inspecionado. Não confundir a prévia Cloudflare do PR (jogo existente) com implementação nova da fazenda.
- O centralizador estava defasado em relação à branch do Claude. Esta atualização incorpora os fatos mais recentes e preserva abaixo o histórico.
- Pedido visual do Eric continua: a prévia do Codex deve seguir a fazenda idle; o rascunho anterior de pomar com caldeirão não representa a direção atual.

## Referência e evidência
- Codex leu a página pública do app e a apresentação https://pokeidle.io/; não entrou em conta nem testou transações ou saques.
- A apresentação anuncia Coins para uso interno, Diamantes para loja e Gemas negociáveis com saque em USDT. São declarações do operador; não são confirmação independente de reservas, pagamentos ou resultados.
- Eric explicitou interesse em oportunidade de ganho para jogadores e rentabilidade do estúdio. Estudar a viabilidade faz parte da direção desejada; três moedas, cripto, provedores, pagamentos e regras de saque ainda não foram escolhidos ou autorizados para operação.

## Frente exclusiva criada — autorização de 14/11/2026
- Eric pediu uma branch própria para trabalhar nesta direção e transmitir o contexto ao Claude. Autorizou opcionalmente um novo repositório; Codex escolheu manter o reuso inicialmente em branch.
- Repositório: [Mendesoz/frutodromo](https://github.com/Mendesoz/frutodromo). Branch: [codex/frutodromo-online](https://github.com/Mendesoz/frutodromo/tree/codex/frutodromo-online), base `b475703`.
- Preparação: `dc354f9` registra a área; `e3de04d` adiciona [documentação própria](https://github.com/Mendesoz/frutodromo/tree/codex/frutodromo-online/docs/online).
- [Brief](https://github.com/Mendesoz/frutodromo/blob/codex/frutodromo-online/docs/online/BRIEF.md), [economia/divulgação](https://github.com/Mendesoz/frutodromo/blob/codex/frutodromo-online/docs/online/ECONOMY_AND_GROWTH.md) e [handoff](https://github.com/Mendesoz/frutodromo/blob/codex/frutodromo-online/docs/online/CLAUDE_HANDOFF.md).
- Somente documentos foram alterados; sintaxe dos dois JS e diff sem erros. Não foram executados novos testes de jogabilidade, nem implementadas mecânicas online ou integrações financeiras.
- Responsáveis: Codex organiza conceito, economia e base técnica; Claude recebe uma tarefa de revisão somente leitura; Eric decide conceito e primeira implementação.
- Comunicação com Claude: entrega e resposta confirmadas em chamada dedicada do Claude Code pelo terminal, com ferramentas somente leitura. O processo concluiu com sucesso; o checkout permaneceu limpo. A mensagem não foi injetada na conversa antiga do aplicativo.
- Revisão e síntese publicadas no commit `a26b439ef01f349ed0b3f1ca60bdcf167033e3d9`: [parecer do Claude](https://github.com/Mendesoz/frutodromo/blob/codex/frutodromo-online/docs/online/CLAUDE_REVIEW_2026-11-14.md) e [próximos passos propostos](https://github.com/Mendesoz/frutodromo/blob/codex/frutodromo-online/docs/online/NEXT_STEPS.md).
- Pontos centrais do parecer: demonstrar demanda e consumo, limitar a reprodução e planejar estado autoritativo no servidor antes do mercado confiável. Não são resultados de teste de jogadores.
- Primeira experiência candidata: duas estufas/slots, três linhagens, um cruzamento e três encomendas consumíveis, em protótipo isolado; o detalhamento ainda precisa ser definido com Eric. Nenhum servidor foi contratado ou código de jogo implementado.
- Estudo de ganho de jogadores permanece parte da direção; custos, requisitos e regras de uma eventual operação de pagamentos/saques ainda precisam de pesquisa e decisão concretas.
- Não promover esta frente para main ou publicar. Preservar saves do lançamento. Um protótipo futuro terá entrada e armazenamento próprios.

## Hipótese de jogo proposta pelo Codex
Uma expansão com pomares mágicos, cruzamento de variedades, produção gradual e mercado entre jogadores.
Ciclo proposto: obter sementes → cultivar → colher → cruzar → atender pedidos ou negociar → ampliar o pomar.
Exemplo de decisão: usar uma fruta rara num pedido rentável agora ou investir em obter uma linhagem produtiva.
Frutas/colheitas seriam consumíveis; sementes ou matrizes teriam função distinta. As regras de reprodução e consumo precisam ser prototipadas para que linhagens raras não gerem oferta sem limite.
Exemplo de interação: um produtor de frutas de gelo vende a um especialista em receitas que consomem esse ingrediente. A utilidade cria demanda; raridade isolada não garante comprador nem preço.

## Reaproveitamento confirmado por leitura de código
No checkout local do Frutódromo: sprites procedurais, atributos e cruzamentos, variedades brilhantes, árvore de espécies, cartas, pedidos de clientes, interface de toque/retrato e áudio.
Inspeção de js/game.js: cross() e sorteios executam no cliente; estado é salvo no localStorage e no módulo de dados do SDK quando disponível.
O atual save, inclusive cópia na nuvem, não é uma autoridade confiável para saldos ou itens negociáveis.

## Trabalho novo necessário para uma economia compartilhada
Contas e servidor responsável por inventários, sorteios, tempo de produção, saldos e transações atômicas; histórico de operações e prevenção de duplicação.
Primeira prova sugerida: pomar pequeno, colheita gradual, cruzamentos e mercado com moeda interna; medir se jogadores produzem, consomem e negociam por interesse no jogo.
Saques e dinheiro real constituem uma etapa própria de produto/operação, sujeita a confirmação de escopo e viabilidade; não foram implementados ou aprovados.

## Relação com a fila
A versão atual do Frutódromo para o portal permanece com o envio manual assumido pelo Eric.
Esta exploração não muda o build aprovado, não confirma envio ao CrazyGames e não substitui automaticamente a ideia de matemática ou os outros projetos da fila.
