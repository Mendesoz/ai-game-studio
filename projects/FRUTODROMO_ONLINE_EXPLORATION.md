# Frutódromo online — exploração de conceito

Data: 14/11/2026. Estado: preparação da frente e coordenação com Claude autorizadas; conceito detalhado e implementação ainda em definição.
Eric indicou https://pokeidle.io/app e perguntou se seria possível produzir algo semelhante com o Frutódromo, após destacar o mercado interno e três moedas da referência.

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
