# SEJUSP Integra — Especificação do dashboard HTML

**Etapa 6.** Documento de especificação para o cenário fictício; o arquivo `dashboard.html` ainda não foi criado. A execução proposta usa comunicação direta entre agentes, conforme [05-tarefas-e-roteiro.md](05-tarefas-e-roteiro.md), conforme as definições de [02-processo-e-dados.md](02-processo-e-dados.md).

## Finalidade e perguntas

| Pergunta do profissional | Informação / visualização | Fonte e atualização |
|---|---|---|
| O que está acontecendo? | Incidentes e local informado, estado e última atualização. | Afirmações extraídas e revisões humanas com IDs. |
| O que precisa de confirmação? | Fila de pendências, responsável sugerido e referências. | Consultas dos agentes e registros humanos. |
| Há relatos divergentes? | Afirmações lado a lado, cada uma com fonte e horário. | Comunicações preservadas; resolução apenas humana. |
| Quais informações dependem de outra força? | Lista de dependências, destinatário e resposta ou aguardando. | Consultas efetivas registradas pelo coordenador. |
| O que mudou desde o último retrato? | Linha do tempo das comunicações e revisões, com data/hora. | Registros de entrada e revisão; sem excluir versões anteriores. |

## Quem faz o quê

O **agente Coordenação** lê cada lote liberado, consolida as respostas e prepara o estado estruturado. PM, Bombeiros e Polícia Científica analisam suas áreas; o agente gera um retrato preliminar; os **representantes humanos** o revisam e registram decisões para uma versão revisada. A Coordenação gera `dashboard.html` no Drive e é a única escritora proposta. O facilitador verifica arquivo e horário; se não houver escrita, salva o conteúdo produzido manualmente.

As rotinas ainda não foram integradas nem testadas e não garantem a gravação do painel. A primeira versão deve apresentar o aviso PRELIMINAR / AGUARDANDO REVISÃO; depois das decisões humanas, uma nova versão as registra e identifica seu estado. O painel mostra informações e revisões; não despacha, não decide prioridade, não verifica identidade e não estabelece que vias sejam seguras. Sua atualização acontece ao regenerar o arquivo após cada lote e revisão; **não é em tempo real**.

## Organização e estados

Um único HTML autocontido, identificado como **SIMULAÇÃO — NÃO OPERACIONAL**, com `ocorrencia_id`, `execucao_id`, lote, versão e horário da geração no cabeçalho. Seções:

1. **Resumo:** quantidade de comunicações recebidas e pendências abertas; contagens de registros, sem estimar pessoas afetadas.
2. **Incidentes:** local informado, tipo, estado do incidente e afirmações com seus próprios estados. Associação proposta deve aparecer como proposta.
3. **Pendências e dependências:** questão, instituição ou papel sugerido, estado e última atualização.
4. **Divergências:** valores conflitantes sem unificação, cada um com IDs e trechos de origem.
5. **Linha do tempo:** comunicações, revisões e decisões humanas separadas por autor e horário.
6. **Detalhe das fontes:** ID, fonte, canal, horário de recebimento e trecho ou texto; omitir detalhes pessoais do painel compartilhado.

Cada afirmação deve mostrar `relatado`, `confirmado`, `contestado` ou `desatualizado`, de acordo com a etapa 2. Uma confirmação simulada atribuída no CSV é identificada como tal e não se confunde com revisão de um participante. Hora de geração não é hora da fonte. Se houver falha ou resposta pendente, mostrar no painel.

## Contrato mínimo de dados

O coordenador produz um arquivo de estado por execução, por exemplo `estado.json`, e usa essa versão para gerar o HTML. O esquema abaixo é o contrato proposto; não pressupõe ferramenta já disponível.

```json
{
  "ocorrencia_id": "SA-ENCHENTE-01",
  "execucao_id": "EX-001",
  "lote_atual": 1,
  "versao": 1,
  "estado_revisao": "aguardando_revisao",
  "gerado_em": "2026-03-18T14:00:00-04:00",
  "comunicacoes_processadas_ids": ["COM-001"],
  "incidentes": [{
    "id": "INC-001",
    "local_informado": "Escola Municipal Caminhos",
    "tipo": "situacao_da_escola",
    "estado": "em_avaliacao",
    "afirmacoes": [{
      "descricao": "Há crianças no prédio, segundo relato.",
      "verificacao": "relatado",
      "fontes": [{"comunicacao_id": "COM-001", "trecho": "ainda há crianças no prédio", "recebido_em": "2026-03-18T13:40:00-04:00"}]
    }]
  }],
  "pendencias": [],
  "consultas": [],
  "revisoes": [],
  "falhas": []
}
```

Exemplo ilustrativo; `gerado_em` real deve ser a hora da geração, não um valor fixo. Cada pendência deve conter ID, questão, responsável sugerido, estado, referências e atualização. Cada consulta deve conter remetente, destinatário, pergunta, resposta ou `aguardando` e horário. Cada revisão deve conter autor, papel, ação, justificativa, referências e horário. Quantidades ausentes são `null`; não usar zero para indicar desconhecido.

**Indicadores:** comunicações processadas = número de IDs únicos efetivamente processados no lote ou execução; pendências abertas = número de registros com estado `aberta`. Mostrar período/escopo e não contar duplicadamente comunicações. Não apresentar número de vítimas, atendimentos concluídos ou recursos disponíveis sem registros revisados e regra explícita.

## Atualização e preservação

O coordenador lê a versão anterior, aplica registros novos e revisões em ordem, incrementa `versao` e gera o HTML. Uma única escrita por vez evita sobrescrita concorrente. O facilitador confere que o novo arquivo contém ocorrência, execução, lote e versão corretos. Preservar versões anteriores ou histórico equivalente; não sobrescrever o CSV. Informações recebidas depois da geração somente aparecem no próximo retrato.

O mecanismo concreto de leitura, escrita e versionamento no Drive depende das permissões da instalação e precisa ser testado. Se houver falha, manter a versão anterior, comunicar o problema e não apresentar uma versão nova como salva. O HTML deve abrir sem servidor e não depender de bibliotecas externas, se a plataforma permitir gerar esse formato; se a visualização no Drive não executar HTML, baixar e abrir em navegador local.

## Revisão após o primeiro retrato

1. A Coordenação registra respostas recebidas e aguardadas e gera `dashboard.html` com estado `aguardando_revisao`, sem converter propostas em fatos confirmados.
2. Delacyr abre o arquivo no Drive, examina fontes e pendências e comunica suas decisões no canal; se o Drive não renderizar, baixa e abre localmente.
3. A Coordenação registra autor, horário, decisões e referências, conserva o histórico e publica nova versão `revisado` ou `parcialmente_revisado`, conforme as pendências remanescentes. Falha de gravação é informada sem anunciar sucesso.

## Aceite mínimo

- Lote 1 é representado sem dados de lotes ainda não liberados.
- Os IDs e trechos exibidos correspondem às comunicações fornecidas.
- Contradições permanecem visíveis; confirmações simuladas e revisões humanas são distintas.
- Uma revisão humana altera o retrato seguinte, com histórico e horário.
- O facilitador consegue localizar e abrir o arquivo gerado ou recebe o conteúdo para salvamento manual.
- Nenhuma informação de outra ocorrência ou execução aparece no retrato.

Estes critérios são propostos; nenhum foi executado ainda. A carga atual contém só uma ocorrência, portanto o último teste exige outra carga fictícia.
