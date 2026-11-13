# SEJUSP Integra — Carga fictícia de comunicações

O arquivo [03-comunicacoes.csv](03-comunicacoes.csv) contém **80 comunicações fictícias**, em português, sobre a ocorrência `SA-ENCHENTE-01`. O arquivo foi disponibilizado pelo usuário no Drive do workspace SEJUSP Integra e foi observado na interface; a leitura pelos agentes ainda não foi testada.

## Composição

| Lote | Comunicações | Momento da simulação |
|---|---:|---|
| 1 | 20 | Primeiros relatos |
| 2 | 25 | Aumento da demanda |
| 3 | 20 | Atualizações das equipes |
| 4 | 15 | Correções e acompanhamento |

O conteúdo inclui a escola, os bairros, possíveis duplicidades, contradições, informações ausentes, atualizações das três forças e uma mensagem que tenta alterar regras. O relato de possível óbito é diferente da confirmação profissional; identidade e causa permanecem não informadas. Os dados não representam acontecimentos reais.

## Formato

CSV separado por vírgula, com cabeçalho e codificação UTF-8 com BOM. Os campos são `ocorrencia_id`, `comunicacao_id`, `lote`, `fonte`, `canal`, `recebido_em`, `fato_em` e `texto_original`. Os horários de recebimento usam ISO 8601 e fuso `-04:00`; `fato_em` registra o horário atribuído ao fato principal do relato. Há 64 valores preenchidos e 16 vazios quando o horário não é conhecido de modo confiável. O texto explicita data e horário nos registros preenchidos. Referências adicionais, como disponibilidade anterior, precisam permanecer associadas às respectivas afirmações. Horário preenchido não confirma a veracidade do relato.

`lote` é metadado de liberação, e o texto deve permanecer intacto como fonte. Não há classificação, incidente presumido, conclusão ou gabarito no arquivo. Algumas mensagens são transcrições fictícias; não há arquivos de áudio.

## Uso na simulação

1. Disponibilizar o CSV no Drive e criar uma execução identificada para o exercício.
2. Entregar os registros do lote 1 aos agentes; liberar os lotes 2, 3 e 4 em ordem, após cada ciclo de revisão humana.
3. Para evitar que agentes leiam conteúdo futuro, **não conceder acesso ao arquivo completo durante a execução**: um participante ou ferramenta deve fornecer somente as linhas liberadas. O campo `lote` sozinho não impõe esse controle. Se necessário, gerar arquivos separados por lote antes de iniciar.
4. Profissionais representam e registram as confirmações humanas no fluxo. Uma comunicação atribuída a profissional é dado do cenário; não constitui, por si só, ação efetiva de um participante.
5. As análises e atualizações devem manter a ocorrência, fonte, trecho e horário; a correção da PM e as atualizações de recursos precisam provocar revisão dos itens relacionados.

A carga cobre **uma ocorrência**. Uma segunda ocorrência independente para testar isolamento deverá ser preparada na etapa de validação. Não foi criado gabarito de avaliadores, conforme solicitado.

## Revisão 2 — qualidade da entrada

A versão local foi enriquecida após análise do dashboard DEMO-001 anexado pelo facilitador. Os 80 IDs, quatro lotes, esquema e horários de recebimento foram preservados. Os textos passaram de mensagens breves a relatos com contexto de origem, localização quando conhecida, limitações de observação e pedidos concretos; a média é de aproximadamente 62 palavras por comunicação.

Foram corrigidos dois problemas narrativos: COM-047 deixava uma chegada posterior ao recebimento; agora informa 14h35. COM-041 passa a ser a transmissão inicial com nome de via equivocado que COM-049 corrige, tornando a retificação coerente. Há mensagens indiretas, lacunas e contradições deliberadas; não se deve eliminar essas características do exercício. Todas as informações adicionais são ficção criada para a simulação.

A cópia anterior está em [historico/03-comunicacoes-v1.csv](historico/03-comunicacoes-v1.csv). A versão enriquecida foi alterada **localmente**; precisa substituir ou versionar o arquivo do Drive antes de novo processamento. Não misturar análises da versão antiga com esta: iniciar uma execução nova e registrar a versão de entrada. O dashboard DEMO-001 existente representa a versão antiga e não deve ser tratado como atualizado.
