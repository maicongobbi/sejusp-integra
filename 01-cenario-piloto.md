# SEJUSP Integra — Cenário piloto

## Identificação

- **Etapa:** 1 — Definição do cenário piloto.
- **Situação:** proposta para validação pelos participantes.
- **Workspace:** SEJUSP Integra, já instalado e configurado no agentes.chat.
- **Ocorrência:** enchente repentina em área urbana, com uma escola isolada e famílias solicitando ajuda em vários pontos da cidade.
- **Local:** Santa Aurora, município fictício de Mato Grosso do Sul.
- **Participantes principais:** profissionais da Polícia Militar, do Corpo de Bombeiros Militar e da Polícia Científica.
- **Natureza dos dados:** inteiramente fictícios, destinados à oficina de elaboração do projeto final do curso.

## 1. Situação inicial

Uma chuva intensa atinge Santa Aurora. Durante a tarde, o nível de um córrego sobe rapidamente e afeta três bairros.

Na Escola Municipal Caminhos, estudantes e funcionários aguardam orientações para uma saída segura. Alguns responsáveis estão tentando chegar ao local, enquanto outros procuram informações sobre os filhos. Entre os estudantes há pessoas que precisam de apoio de mobilidade.

Ao mesmo tempo, chegam pedidos de ajuda de residências alagadas, notícias de veículos imobilizados e informações sobre vias bloqueadas. Equipes da PM e dos Bombeiros já estão em campo e enviam atualizações.

As informações chegam em momentos diferentes e com níveis variados de precisão. A mesma situação pode ser relatada por um morador, um familiar e uma equipe, usando endereços ou pontos de referência diferentes.

## 2. Problema central

> Como transformar um grande volume de comunicações em informações verificáveis para que PM e Bombeiros compreendam as necessidades, esclareçam pendências e coordenem os atendimentos?

A dor aparece quando uma informação importante fica dispersa: uma equipe recebe o pedido de ajuda, outra conhece uma restrição de acesso e uma terceira atualização informa que o atendimento já começou.

O sistema precisa ajudar os profissionais a perceber essas relações, preservando o que ainda não foi confirmado.

## 3. Componente humano e impacto social

A história que aproxima o público da ocorrência é a de uma responsável que procura notícias da filha:

> “Disseram no grupo que retiraram todas as crianças, mas a escola ainda não confirmou. Minha filha precisa de ajuda para se locomover. Ela continua lá?”

Esse pedido exige distinguir rumor, informação institucional e atualização de equipe. Também pode revelar uma necessidade específica que deve chegar aos responsáveis pelo atendimento.

O benefício social pretendido é reduzir perdas de informação e atrasos de coordenação que afetam pessoas aguardando ajuda. O protótipo poderá demonstrar melhora no tratamento das informações; efeitos sobre o atendimento real exigiriam validação posterior.

## 4. Participação das forças e demais atores

| Participante | Contribuição no cenário |
|---|---|
| Bombeiros | Informações sobre necessidades de salvamento, atendimentos em andamento e recursos técnicos necessários, conforme avaliação profissional. |
| PM | Informações sobre isolamento, bloqueios, segurança e apoio à circulação ou retirada de pessoas, conforme suas atribuições e protocolos. |
| Polícia Científica | Recebe solicitações periciais e registra informações de sua competência sobre possíveis óbitos, identificação e exames, conforme o exercício. |
| Coordenação humana | Validação de informações, esclarecimento de conflitos e decisões sobre encaminhamentos. |
| Escola, moradores e familiares simulados | Origem de relatos, solicitações e atualizações; não precisam ser participantes adicionais do grupo. |

As atribuições são convenções da oficina. Esta proposta não estabelece um protocolo operacional oficial.

## 5. Volume e natureza das comunicações

O conjunto proposto contém **80 comunicações fictícias**, distribuídas em quatro lotes. A ocorrência representa algumas horas; os lotes podem ser liberados rapidamente durante o exercício.

| Lote | Conteúdo predominante | Quantidade |
|---|---|---:|
| 1 — Primeiros relatos | Alagamentos, dúvidas sobre a escola e solicitações iniciais. | 20 |
| 2 — Aumento da demanda | Novos pedidos, repetições e endereços incompletos. | 25 |
| 3 — Atualizações das equipes | Confirmações, atendimentos iniciados e restrições de acesso. | 20 |
| 4 — Correções e acompanhamento | Informações corrigidas, pendências e atendimentos concluídos. | 15 |
| **Total** | | **80** |

O conjunto terá mensagens curtas, registros mais extensos e transcrições simuladas de comunicações por voz. Entre elas:

- Relatos diferentes sobre o mesmo incidente.
- Informações contraditórias sobre a situação da escola.
- Endereços incompletos e locais descritos por referências.
- Atualizações que tornam mensagens anteriores desatualizadas.
- Pedidos que dependem de informação das duas forças.
- Mensagens que não contêm elementos suficientes para um encaminhamento.

As mensagens individuais estão em [03-comunicacoes.csv](03-comunicacoes.csv); não há gabarito separado.

## 6. Recorte do processo

A tarefa repetitiva a estudar será **receber, registrar, classificar, relacionar e atualizar comunicações da ocorrência**, encaminhando dúvidas e pendências aos responsáveis.

O resultado esperado é um conjunto de incidentes organizado, com fontes, horários, situação conhecida e informações ainda necessárias para decisão.

A estrutura dos agentes e do dashboard será definida a partir desse processo nas próximas etapas. O ambiente deverá permitir a colaboração entre especialistas de IA e profissionais humanos, inclusive correções durante o processamento.

## 7. Limites do piloto

- A ocorrência é fictícia e não envolve acionamento de serviços reais.
- Decisões de despacho de equipes, avaliação clínica e determinação de rotas seguras permanecem com profissionais autorizados.
- Relatos recebidos não são tratados automaticamente como fatos confirmados.
- A escola será o ponto de maior apelo emocional, mas o exercício também terá incidentes nos bairros.
- A duração simulada da ocorrência é distinta do prazo de quatro horas da oficina para elaboração do projeto.
- O cenário é um piloto do SEJUSP Integra; não limita o ambiente a enchentes.

## 8. Hipóteses a validar na próxima etapa

- Canais de comunicação e formatos mais representativos da experiência dos participantes.
- Responsáveis pela recepção, validação e atualização das informações.
- Categorias de incidentes e critérios para classificação.
- Procedimentos de consulta e coordenação entre PM e Bombeiros.
- Critérios para confirmar, corrigir e encerrar um registro.
- Adequação do volume proposto ao processamento disponível no ambiente.

## 9. Definição consolidada

Uma enchente urbana fictícia em Santa Aurora, abrangendo três bairros e uma escola isolada, com 80 comunicações progressivas e foco no tratamento compartilhado das informações pela PM, pelos Bombeiros e pela Polícia Científica.

Este documento define o cenário piloto. O próximo entregável será o mapeamento do processo e a definição do significado dos dados, incluindo AS-IS, TO-BE e a separação entre REGRA, LLM e HUMANO.
