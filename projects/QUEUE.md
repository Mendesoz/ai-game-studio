# Fila de jogos do AI Game Studio

Atualizada em 19/11/2026. Solicitação do Eric: manter uma fila e iniciar o próximo jogo à medida que o anterior for concluído.

## Fila atual
| Ordem | Projeto | Estado | Próximo passo | Responsáveis |
|---|---|---|---|---|
| 1 | [Brotalume — nome de trabalho](BROTALUME_STATUS.md) | Produto principal; mapa ativo é o composto por código; arte gerada fica como referência de atmosfera | Refinar chão, plantas, galinhas e luz no mapa codificado; conferir no telefone e apresentar ao Eric | Codex + Claude; Eric decide design |
| 2 | [Frutódromo original (legado)](FRUTODROMO_STATUS.md) | Site publicado; histórico do rascunho CrazyGames preservado; CrazyGames saiu do escopo atual | Manutenção somente se necessária | Codex + Claude conforme surgir demanda |
| 3 | [Matemática como jogo de aventura/estratégia](MATH_GAME_EXPLORATION.md) | Ideia apresentada; gênero e conceito em discussão, sem produção aprovada | Primeiro caso: FUVEST 2013 Q23, Eratóstenes; discutir mecânica a partir da questão; Coquinhos é referência do que evitar | Codex + Claude no escopo; Eric decide o conceito |
| 4 | [Perseguição e fuga no navegador](NEXT_GAME_EXPLORATION.md) | Exploração anterior preservada no backlog; sem escopo aprovado | Retomar quando Eric priorizar | Eric + agentes |

## Como avançar
- Manter um jogo principal em produção. Brotalume é o projeto atual; o Frutódromo original fica como legado.
- A fila organiza trabalho, mas não dispara agentes nem autoriza gastos ou publicação automaticamente.
- Só avançar para produção após o Eric aprovar conceito e escopo. Usar [GAME_BRIEF.md](../templates/GAME_BRIEF.md).
- Manutenção e bugs críticos dos jogos publicados têm prioridade, sem recolocar CrazyGames no escopo do Frutódromo.

## Registro de decisão
- 14/11/2026, Eric: quer uma fila contínua de jogos e explorar multiplayer; citou Dead by Daylight e PEAK como referências, sem conceito concreto.
- 14/11/2026, Eric: no Frutódromo, aprovou corrigir só os pesos negativos; manter nesta versão progressão, VIP, registro de erro/acerto e dificuldade por aparelho.
- Meta de trabalho para o Frutódromo: tentar preparar o reenvio em 14/11/2026, condicionado à conclusão e aprovação dos itens pendentes. Não é promessa de publicação na mesma data.

- 14/11/2026, Eric: próxima ideia é transformar situações matemáticas de ENEM/vestibulares em jogabilidade; rejeitou Coquinhos como referência e não quer formato de plataforma de exercícios. Gênero, tecnologia, modelo de venda e eficácia ainda não definidos.

- 14/11/2026, Eric: autorizou branch separada e handoff ao Claude para explorar Frutódromo idle com mercado; destacou divulgação e oportunidade de ganho de jogadores. Branch criada: `codex/frutodromo-online`. Ainda não há aprovação de regras financeiras ou implementação do jogo completo.

- 15/11/2026, conferência Codex: oito commits do Claude no PR #27; mudança registrada para fazenda idle, sem genética. Atualização da ficha distingue decisões relatadas, propostas, simulação e artifacts privados. Nenhuma implementação nova da fazenda identificada no diff do repositório.

- 15/11/2026, Eric: referência é gameplay de Hay Day, com nossa identidade/sprites, fazenda personalizada e sem caldeirão. Pediu novo nome; proposta do Codex: Brotalume. PR #29 reúne as duas frentes; comunicação direta por CLI falhou por autenticação expirada e o alinhamento foi publicado no PR, sem resposta confirmada.

- 15/11/2026, Eric: autorizou seguir a base recomendada, construir banco/backend e incluir Claude para acelerar, buscando algo concreto até30/11. Plano no PR#30/issue#31; datas são metas. Não autoriza pagamentos/saques ou publicação comercial. Base técnica validada; cliente conectado/comércio são próximos marcos.

- 16/11/2026: mapa/cliente online concluídos no piloto local, antes do alvo19–22/11. Comércio P2P segue próximo; backend público, ligas e pagamentos não entregues. Conferir ficha e QA, não a prévia Cloudflare histórica.

- 17/11/2026, Eric: a fazenda online substitui o Frutódromo como produto; CrazyGames sai do escopo; jogadores financiam o negócio e eventual retorno sacável faz parte da hipótese. Estrutura de receita/saque permanece sem decisão. Expansão híbrida aprovada.
- 17/11/2026, Eric: escolheu a composição A, pátio central, como base visual para prototipar; não equivale à aprovação da arte final.
- 19/11/2026, Codex: cena A navegável montada em canvas local e aberta no browser. Caminhada simples, caminhos, casa, dois canteiros, galinheiro, bosque e clareira; assets reaproveitados do renderer existente. HTTP local e túnel responderam; não houve QA em iPhone físico. Arquivos estão na árvore local de `codex/fazenda-online-base`, sem commit/push.
- 19/11/2026, Eric: gostou da primeira proposta gerada e pediu um protótipo de jogo funcional que use a ilustração, para comparar com a versão feita por código. Codex entregou a rota gerada com avatar, movimento, produção temporal e coleta de teste. Arte não está aprovada como final; o cenário único não dá ainda suporte a edição/expansão dos objetos.
- 19/11/2026, Eric: pediu continuar sem usar a arte gerada como fundo, melhorando a versão por código com ambientação, galinhas móveis e plantas com forma/volume. Codex adicionou duas galinhas passeando/ciscando, canteiros folhosos e de morangos, balanço de folhas/flores, borboletas e fumaça da chaminé. Prévia no browser; sem teste físico em iPhone, sem integração ao mapa real.

- 16/11/2026: etapa3 fechada antes do alvo23–26/11: negociação virtual na UI e44testes PostgreSQL verdes. Próximo etapa4. Claude confirmou handoff41ef83e; VIP/comissão do protótipo separado seguem na descoberta. Ver ficha atual para SHAs e evidências.

- 16/11/2026: Eric separou visual/funcional e pediu WASD; referências visuais Stardew/Don't Starve/Sunflower. Cenário candidato e caminhada integrados, ainda sem aprovação estética. Onboarding e issues32–35 para Gabriuus preparados; read confirmado, atribuição recusada, nenhum convite enviado. Ver ficha para QA/CI/limites.

- Gabriel conduzirá seu próprio Claude: issues33/35 são implementação de ajuda HTML/CSS e arte canvas isolada, com PR/revisão; não apenas tarefas manuais ou relatórios.
