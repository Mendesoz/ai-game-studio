# Brotalume — arquitetura de fazendas e regiões

**Estado:** direção aprovada por Eric para planejamento em 20/11/2026. Ainda precisa ser convertida em especificações por marco antes da implementação. Brotalume continua sendo nome de trabalho.

## Modelo de mundo

- Cada jogador possui uma fazenda própria e persistente, com plantações, animais, máquinas e construções.
- O proprietário pode receber visitas assíncronas mesmo estando offline. A visita lê o estado autorizado da fazenda; não depende de manter o dono conectado nem de sincronização contínua de avatares/posições.
- A economia é compartilhada entre jogadores por um mercado global.
- Além da fazenda principal, o mundo pode ter regiões especializadas. O jogador as desbloqueia por progressão, recursos e missões. Bosque (frutas, madeira, mel e recursos naturais) e Porto (pesca, expedições e comércio marítimo) são exemplos iniciais, não lista final aprovada.
- Cada região é carregada separadamente, para limitar memória e trabalho ativo no cliente.

## Regras técnicas aprovadas

1. **Produção offline por timestamps.** Persistir no backend os horários necessários de início/conclusão e calcular a produção quando houver uma ação/leitura válida. Não manter uma simulação contínua de todas as fazendas.
2. **Autoridade do servidor.** O backend valida colheitas, inventário, negociações e recompensas. O cliente apresenta o estado e solicita ações; não decide sozinho saldos ou resultados econômicos.
3. **Visitas assíncronas.** Não exigir conexão simultânea entre visitante e proprietário, nem sincronização constante de posições dos jogadores.
4. **Regiões modulares.** Carregar só a região em uso. Dados, regras e apresentação de novas áreas devem permitir expansões futuras sem manter todos os mapas ativos.
5. **Eficiência.** Priorizar consumo baixo de servidor e compatibilidade com dispositivos modestos; evitar tick global/por fazenda quando timestamps resolvem o cálculo.

## Ordem de implementação aprovada

1. Consolidar a fazenda principal e a produção offline.
2. Implementar visitas assíncronas a fazendas.
3. Consolidar o mercado global.
4. Criar a primeira região desbloqueável.
5. Expandir o mundo de acordo com retenção e demanda observadas.

Essa ordem é prioridade de planejamento, não uma declaração de que as etapas já estejam implementadas ou prontas para produção. O status técnico de cada etapa deve ser confirmado no repositório do jogo e registrado na [ficha do projeto](BROTALUME_STATUS.md).

## Decisões a detalhar antes de cada marco

- Visitas: quem pode visitar, controles de privacidade, quais ações são apenas leitura e como evitar alterações não autorizadas.
- Produção offline: fórmulas, limites temporais, capacidade de armazenamento, efeitos de upgrades e comportamento de relógio inconsistente.
- Mercado: catálogo/itens negociáveis, preço e taxas, concorrência de listagens, expiração/cancelamento, idempotência, fraude e auditoria.
- Desbloqueios: custos e condições de progressão de cada região e como missões/recompensas entram na economia.
- Regiões: contrato de dados, carregamento/descarregamento, persistência compartilhada e limite de conteúdo carregado.

Estes pontos são requisitos para especificação futura, não decisões tomadas nem autorização para criar pagamentos/saques. A monetização com dinheiro real continua em discovery conforme a ficha de Brotalume.

## Evidência e escopo

- Decisão recebida de Eric em 20/11/2026 e registrada no centralizador. Nenhum teste de software ou integração de código foi executado nesta atualização documental.
- Repositório do jogo: [Mendesoz/frutodromo](https://github.com/Mendesoz/frutodromo), branch de trabalho registrada na ficha. Código e commits precisam ser conferidos antes de iniciar cada etapa.
