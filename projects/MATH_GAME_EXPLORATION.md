# Próximo jogo — matemática como jogabilidade

Status: ideia apresentada pelo Eric; conceito, gênero, arte, tecnologia e produção ainda não aprovados.
Data: 14/11/2026.
Nome comercial: a definir.
Fila: [QUEUE.md](QUEUE.md).
Repositório do jogo: ainda não criado.

## Direção do proprietário
Criar um jogo de verdade que torne compreensíveis situações e raciocínios de problemas matemáticos, incluindo os encontrados no ENEM e em vestibulares como a FUVEST. O interesse inclui interpretar enunciados longos e reconhecer as relações entre informações, além de executar contas.

Começar por matemática; outras matérias são uma possibilidade futura. Plataforma e tower defense foram exemplos levantados para explorar, não gêneros escolhidos. Existe interesse comercial futuro em redes e secretarias de educação; é hipótese de mercado, sem demanda, venda ou resultado de aprendizagem demonstrados.

A proposta se baseia em transformar o raciocínio em ações e consequências dentro de um mundo de jogo. O Eric rejeitou formatos semelhantes a Duolingo, Kahoot, plataformas de exercícios ou jogos genéricos com atividades escolares. Não há autorização para implementar uma plataforma administrativa.

## Referência do que evitar — determinação explícita do Eric
https://www.coquinhos.com/tag/jogos-de-matematica/

O site foi fornecido como NÃO referência. Codex leu o catálogo e as descrições de dois exemplos:
- [Tiro Matemático](https://www.coquinhos.com/tiro-matematico-calcule-somas-e-subtracoes-e-atire/): resolver uma operação e acertar o alvo com a resposta.
- [Math Speed Racers](https://www.coquinhos.com/math-speed-racers-corridas-matematicas-1-a-4-jogadores/): responder operações para fazer o veículo avançar.

Usar esses exemplos para identificar padrões rejeitados, sem generalizar a análise a todos os jogos do catálogo. Evitar:
- Exercício de conta ou múltipla escolha como requisito para destravar uma ação de jogo independente.
- Trocar apenas personagens, cenário e recompensas de uma lista de exercícios.
- Catálogo de minijogos por operação como identidade do produto.
- Tratamento infantil por padrão para um projeto ligado a estudantes de ensino médio.
- Contagem de pontos ou rapidez de cálculo como única evidência de compreensão.

## Unidade de design esclarecida pelo Eric
O ponto de partida é uma questão concreta fornecida pelo Eric. A partir dela, identificar situação, dados, restrições, relações e incógnita; transformar esses elementos em ações, regras, feedback e objetivo de jogo. O gênero e a ambientação são escolhidos depois dessa análise, em vez de obrigar todas as questões a caber num jogo previamente definido.

Primeiro caso fornecido: [FUVEST 2013, primeira fase, questão 23 — Eratóstenes](MATH_CASE_FUVEST_2013_Q23.md). A demonstração é exploração de mecânica, sem produção de jogo completo aprovada.

## Hipótese de design do Codex — para discutir
O enunciado vira uma situação do mundo; as relações matemáticas viram suas regras. O jogador observa, planeja, manipula, executa e vê o resultado. Números, gráficos e textos curtos podem fazer parte das ferramentas e pistas do mundo.

Proposta inicial: aventura com puzzles de sistemas e construção leve. Exemplo exploratório: preparar uma operação de resgate ou transporte entre ilhas, escolhendo rotas, carga e máquinas sob restrições de tempo, capacidade e recursos. A situação deve ter decisões e consequências próprias, sem pausar a ação para um questionário externo.

| Caminho | Possibilidades | Risco a testar |
|---|---|---|
| Aventura com puzzles de sistemas | Interpretar pistas, experimentar soluções, representar quantidades e relações | Virar uma sequência desconexa de exercícios com cenários diferentes |
| Estratégia/tower defense com planejamento | Taxas, proporções, alcance, orçamento e otimização | Reflexos ou tentativa cega dominarem o raciocínio-alvo |
| Plataforma com puzzles | Escala, espaço, geometria, movimento e trajetórias | Outros conteúdos parecerem acrescentados artificialmente |

Nenhum desses caminhos está aprovado. A referência anterior de perseguição/multiplayer continua no backlog, não foi incorporada automaticamente a este conceito.

## Questão central de aprendizagem
Vencer uma fase não demonstra, por si, compreender um problema novo ou um enunciado de vestibular. O protótipo precisa investigar como o jogador passa de uma representação visual para outra: fala, texto, tabela, gráfico e expressão matemática.

A progressão pode começar concreta e introduzir representações gradualmente. O erro deve produzir uma consequência interpretável e permitir uma nova tentativa. A forma de feedback e a presença de símbolos ainda serão desenhadas.

## Primeiro recorte proposto
- Um ciclo de jogo e um conjunto pequeno de situações envolvendo proporcionalidade e funções, a confirmar com professor de matemática.
- Um protótipo curto, antes de expandir para toda a matemática ou outras matérias.
- Revisão matemática das situações e das regras por especialista.
- Testes separados de vontade de continuar jogando e de compreensão em problemas novos fora do jogo.
- Descobrir a viabilidade de uso com estudantes e professores no equipamento realmente disponível. Um piloto exploratório não prova eficácia nem garante compra institucional.
- Sem compromisso de multiplayer, engine, orçamento, prazo, painel escolar ou produção de conteúdo em escala.

## Fontes consultadas pelo Codex em 14/11/2026
- [Matrizes de referência do ENEM — Inep](https://www.gov.br/inep/pt-br/centrais-de-conteudo/acervo-linha-editorial/publicacoes-institucionais/avaliacoes-e-exames-da-educacao-basica/matrizes-de-referencia-enem): referência de competências e habilidades; não substitui análise das questões.
- [Kacmaz e Dubé, 2022](https://doi.org/10.1016/j.edurev.2021.100428): síntese de pesquisa que distingue abordagens de design e tipos de conhecimento em jogos de matemática; não é evidência da eficácia deste projeto.
- [Slice Fractions — desenvolvedor](https://ululab.com/press-kit-slice-fractions/): precedente de conceitos representados por puzzles físicos, voltado a outra faixa de conteúdo; não é o formato já escolhido para este jogo.

## Próxima decisão
Discutir a experiência desejada e escolher uma situação para converter em jogabilidade. Depois aprovar o conceito e preencher o brief do estúdio. Nenhum código de jogo, contato comercial ou parceria foi iniciado.
