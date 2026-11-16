# Brotalume — fazenda idle (nome de trabalho proposto)

## Cenário, caminhada e entrada de colaborador — 16/11/2026
Esta seção é o ponto de retomada atual; os marcos abaixo preservam o histórico.
- Eric separou **funcionalidade/organização** de **visual da fazenda**. Cenário anterior considerado simples/incongruente com o elenco. [Direção de arte e filas](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/DIRECAO_ARTE.md). Teste funcional verde não significa arte aprovada.
- Referências visuais autorizadas: Stardew Valley, Don't Starve e captura do Sunflower Land enviada pelo Eric; Hay Day permanece referência de gameplay. Reaproveitar identidade original, sem copiar ativos ou importar economia das referências.
- Claude cloud entregou fila funcional/contrato em3f743d7, integrado emce171aa com ressalvas do Codex. Estudo isolado de arteb6186be. Depois, a pedido do Eric, cliente /play/ recebeu cenário candidato, **WASD, colisão, câmera acompanhando e botões móveis**. Claude local implementou módulo puro/11testes; Codex arte/input/integração/QA.
- Código **e4df1fbec9b1a3f7d578cd8cf2e238113d6c256c**, documentação/onboarding **21a266b8b0835ce82541d3ca1751a6248fc330a9**, [PR30](https://github.com/Mendesoz/frutodromo/pull/30). **55/55 PASS local e PostgreSQL17**, [CI43896654461](https://github.com/Mendesoz/frutodromo/actions/runs/43896654461). Tipos/build/auditoria/sintaxe verdes. [QA e imagens](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/QA_CAMINHADA_2026-11-16.md): caminhada/colisão, botão móvel, produção, posição por campos e recarga, anúncio/cancelamento, quatro viewports sem overflow.
- Arte **ainda candidata**. Pose frontal com passos simples; faltam corpos/direções completos, acabamento/transições do terreno e composição com mais espaço para o mundo. Caminhada local, reinicia ao recarregar, sem presença multiplayer. Safari/iPhone físico e arraste após o novo ponto de pega ainda não verificados.
- Eric pediu onboarding do amigo **Gabriuus (Gabriel)** e esclareceu que ele conduz seu próprio Claude Code para implementar, como Eric faz com os agentes. As issues33 e35 exigem código concreto, não apenas propostas. [Guia pronto e prompt](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/ONBOARDING_COLABORADOR.md); fila [32](https://github.com/Mendesoz/frutodromo/issues/32) primeira sessão, [33](https://github.com/Mendesoz/frutodromo/issues/33) ajuda de controles em HTML/CSS, [34](https://github.com/Mendesoz/frutodromo/issues/34) QA e [35](https://github.com/Mendesoz/frutodromo/issues/35) enfeites isolados. Uma por vez, PR para integração, revisão Codex/Eric. Sem delegar economia/banco/autenticação/produção/publicação.
- GitHub confirmou Gabriuus com permissão **read** e recusou atribuição; issues existem sem assignee. Não foi enviado convite nem alterada permissão. Fork/PR pode permitir começar; responsável previsto está nos textos. Nenhuma tarefa iniciada por ele foi presumida.
- Próximas frentes: visual (composição/terreno/personagem direcional) e funcional etapa4 (automação limitada, fila já revisada). Reservas desta rodada liberadas. Preview local http://127.0.0.1:8860/play/ atualizado; sem main, hospedagem pública ou finanças. CI por envio e Claude em chamadas delimitadas, sem serviço permanente.

## Feira online entre contas concluída — 16/11/2026
Esta seção substitui o estado anterior de comércio pendente.
- Etapa3 do plano até30/11 entregue no piloto: anunciar milho/ração/ovo, reservar lote e capacidade, comprar/cancelar atomicamente, consultar própria banca e histórico. Duas contas negociaram pela UI com moedas virtuais resetáveis, sem taxa ou dinheiro real.
- [PR30](https://github.com/Mendesoz/frutodromo/pull/30), branch `codex/fazenda-online-base`. Implementação4f4b6cf, teste8aedd7c, correção finala0622d8d7f1973ff9b1a094ae91134050041ede7; documentaçãof55d50f419dd9a8e84a6d1410cba3673b92f1aba. Main intacta.
- **44/44 testes PostgreSQL17 PASS**, [CI43856745064](https://github.com/Mendesoz/frutodromo/actions/runs/43856745064), build/auditoria/sintaxe verdes. Inclui dois compradores disputando um lote, compra contra cancelamento, compras recíprocas, conservação/replay, total forjado e resgate com lote reservado. Local:43testes da suíte inicial e caso adicional dirigido passaram.
- Navegador: venda2milhos por4moedas; comprador80→76/4→6milhos, vendedor80→84/4→2. Recarga persistente. Segunda compra no celular por3moedas: comprador73/7milhos e vendedor87/1milho. Quatro viewports sem overflow lateral. [QA e capturas](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/QA_MERCADO_2026-11-16.md).
- Claude implementou market.ts/migração004/13testes em arquivos reservados. Codex integrou helpers/API/cliente e executou QA. Revisão independente Claude sem bloqueadores; achado de erro escondido no diálogo corrigido e reproduzido com saldo gasto em outra aba:409 visível, botão bloqueado, saldo atualizado e sem débito/entrega parcial.
- A frente cloud do Claude recebeu estado/PR/CI e confirmou a separação no handoff41ef83e. Seu protótipoe65e26d (VIP negociável/comissão10%) e documento303bbb6 são descoberta separada; não incorporados ao servidor. Conferir essas branches antes de novas decisões, sem reintroduzir caldeirão ou tratar gemas simuladas como moeda real.
- **Prévia local:** http://127.0.0.1:8860/play/ . QA usou localhost/banco separado, depois encerrado. Sem backend público. Safari/iPhone físico, carga, backup/restauração e validação de jogadores ainda pendentes.
- Multicontas/brindes transferíveis, resgate e vitrine limitada são riscos aceitos apenas neste piloto fechado resetável; bloqueiam economia pública. Preços continuam candidatos.
- Próximo: etapa4, automação de reposição com ingrediente mínimo, ciclos/prazo finitos, reserva e equivalência online/offline. Áreas da etapa3 liberadas no roadmap. CI por push e Claude sob demanda; sem serviço permanente de desenvolvimento.

## Mapa e cliente online concluídos — 16/11/2026
Esta seção substitui o estado anterior de API sem cliente.
- Eric pediu continuar o desenvolvimento. Codex entregou cliente jogável com cadastro/login, mapa contínuo, expansão adjacente, produção/encomenda e layout/personagem salvos no servidor.
- [PR #30](https://github.com/Mendesoz/frutodromo/pull/30), branch `codex/fazenda-online-base`. Código validado3d113ecb45435c83291198dd48c2d0e8910677a5, documentação17e20d31d6ec4dd1ed4ff596bae7ebb8cf03c1b1. Sem merge na main.
- **29 testes PASS** local e [PostgreSQL17 real na CI43850499270](https://github.com/Mendesoz/frutodromo/actions/runs/43850499270), build/auditoria/sintaxe PASS. [QA e evidências](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/QA_MAPA_ONLINE_2026-11-16.md).
- Browser real: cadastro, milho→ração→ovo→pedido (+18moedas), terreno60moedas, movimento por campos/arraste/toque, bloqueios de sobreposição/terra alheia, personagem e recarga persistentes. Quatro telas (393×760,1024×600,900×430,1280×680) sem rolagem horizontal; escala inteira1×/2×.
- Guarda adicional: comandos do cliente informam a fazenda esperada; troca de cookie para outra conta é recusada dentro da transação. Caso HTTP automatizado provou zero efeitos na outra fazenda.
- Falha controlada depois de comando confirmado no backend: reenvio pela UI preservou um único débito/item. Poll continuou com pedido pendente. Após401 e entrada em outra conta, pedido anterior descartado, nova fazenda80moedas/4milhos sem reenvio indevido.
- Claude implementou layout, migração003, move/customize e9testes nos arquivos delegados; Codex integrou cliente e executou. Claude também revisou cliente e correções finais, somente leitura; achados pertinentes aplicados. Relatórios no repositório, não presumir comunicação com o chat antigo.
- **Prévia local:** http://127.0.0.1:8860/play/ . Não há backend publicamente hospedado; a prévia Cloudflare antiga permanece um protótipo separado. Frutódromo publicado e saves não alterados.
- Etapa2 do [plano até30/11](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/PLANO_NOVEMBRO.md) concluída antes do alvo. Próximo: etapa3, comércio virtual entre duas contas (reserva de lote, compra/cancelamento atômicos, travas ordenadas e conservação de saldo/estoque). [Fila#31](https://github.com/Mendesoz/frutodromo/issues/31).
- Pagamentos/saques, ligas e hospedagem pública não entregues. Safari/iPhone físico, carga, balanceamento e retenção ainda não medidos. Brotalume permanece nome de trabalho.

## Base online autorizada e validada — 15/11/2026
Esta seção prevalece sobre os registros históricos abaixo.
- Eric autorizou seguir a base proposta pelo Codex, construir banco/backend, incluir Claude e automatizar verificações para buscar um alpha fechado até **30/11/2026**. Meta de desenvolvimento, sem promessa de publicação comercial.
- [PR #30](https://github.com/Mendesoz/frutodromo/pull/30), branch `codex/fazenda-online-base`, derivada da integração visual bce3379. Código validado: `4234e4d968db5ec723973e9ceea9baa1aae5d466`; documentação final:e9a180d. Main, jogo publicado e saves locais preservados.
- Implementado em server/: Node/TypeScript, PostgreSQL, contas/sessões, inventário/razões, filas por tempo do banco, milho→ração→ovo→pedido NPC, compra/resgate limitado de semente e compra de terreno adjacente. PGlite persistente somente para desenvolvimento local; backend público não contratado/configurado.
- **18 testes PASS local e em PostgreSQL17 real**, com duas pools/instâncias,50comandos concorrentes,30replays da mesma chave e capacidade concorrente. Build, auditoria das dependências e sintaxe PASS na [CI43709893238](https://github.com/Mendesoz/frutodromo/actions/runs/43709893238).
- Claude Code autenticou com sucesso após login na extensão e respondeu a duas chamadas dedicadas somente leitura: [parecer da proposta](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/CLAUDE_BASE_ONLINE_2026-11-15.md) e [revisão do código](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/CLAUDE_REVISAO_CODIGO_2026-11-15.md). Aprovou para teste local fechado; não executou testes. Codex aplicou achados pertinentes e ampliou a cobertura.
- Smoke HTTP real: duas contas distintas, fazendas separadas e comando repetido com um único plantio. Servidor compilado local reiniciado com correções e migração002; health200. Nenhuma nova UI/teste de navegador nesta rodada. A prévia visual ainda **não usa esta API**; não anunciar multiplayer jogável.
- [Plano vigente](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/PLANO_NOVEMBRO.md), [QA](https://github.com/Mendesoz/frutodromo/blob/codex/fazenda-online-base/docs/online/QA_BASE_ONLINE_2026-11-15.md), [fila com critérios](https://github.com/Mendesoz/frutodromo/issues/31). Próximo: mapa contínuo + cliente online até22/11; depois negociação virtual entre duas contas, automação limitada e candidata de teste fechado.
- Automação real: CI em cada envio relevante; `npm run review:claude` chama revisor Read/Glob/Grep sem janela, resultado privado. Não há serviço permanente de desenvolvimento ou sincronização da conversa antiga. Implementação ocorre em sessões ativas, sem Eric transportar contexto.
- Preservar arte original, navegador e celular em pé. Ligas/barcos/pagamentos/saques fora do alpha. Nome Brotalume continua proposto.

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
