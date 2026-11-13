# SEJUSP Integra — Fluxo de agentes e roteiro da simulação

**Etapa 5 — fluxo adotado.** Delacyr inicia a simulação no canal `#santa-aurora`, chamando a Coordenação. Os agentes colaboram por consultas diretas; as quatro rotinas existentes ficam pausadas e não fazem parte deste teste. O CSV `03-comunicacoes.csv` está no Drive. Em teste anterior, a Coordenação reportou leitura filtrada de COM-001 e COM-002 e consultou Bombeiros e PM; Bombeiros respondeu. A geração e abertura do HTML no Drive, a consolidação após respostas assíncronas e a revisão completa ainda não foram comprovadas. Tudo é fictício.

**Histórico:** quatro itens no quadro Tarefas foram criados por engano e não integram este fluxo. Seu estado atual não foi conferido. A Coordenação foi instruída a não criar nem alterar tarefas do quadro.

## Quem participa

| Papel humano | Responsabilidade durante a oficina | Quem pode acumular |
|---|---|---|
| **Facilitador / operador** | Prepara a execução, libera a bateria e inicia o coordenador por mensagem, acompanha falhas e registra mensagens; não altera o conteúdo original. | Pode ser o coordenador humano. |
| **Coordenador humano** | Decide associações, resolve ou mantém conflitos, revisa o painel preliminar e registra decisões e correções. | Um participante designado; pode exercer o papel de outra força se faltar gente. |
| **Representante PM** | Examina informações de acesso, bloqueio e segurança, registra confirmações ou correções simuladas. | Pode também representar Polícia Científica. |
| **Representante Bombeiros** | Examina pedidos de salvamento, necessidades e andamento relatado; registra confirmações ou correções simuladas. | Pode também ser coordenador ou facilitador. |
| **Representante Polícia Científica** | Examina solicitação e informação pericial e distingue relato de confirmação atribuída. | Na ausência de participante dessa área, papel didático exercido por alguém designado; não é validação profissional real. |

Com três pessoas: A acumula facilitador e coordenação; B representa PM e Polícia Científica; C representa Bombeiros. Com duas: A acumula facilitação, coordenação e PM; B representa Bombeiros e Polícia Científica. Indicar o papel ao registrar cada intervenção; ninguém precisa se passar por profissional habilitado fora do exercício.

## Responsabilidades dos agentes

- **Quem lê as comunicações?** O agente **Coordenação** lê o lote liberado do CSV, verifica os campos, extrai e classifica propostas, sempre citando o ID e o trecho. Ele envia recortes aos especialistas; estes analisam o que é pertinente à sua área. O facilitador conserva o original e acompanha a leitura.
- **Quem analisa?** Os agentes **PM**, **Bombeiros** e **Polícia Científica** respondem às consultas do coordenador e, quando possível, consultam uns aos outros. Profissionais humanos revisam os achados das respectivas áreas.
- **Quem atualiza o dashboard?** O agente **Coordenação** é o único escritor proposto de `dashboard.html` e da cópia estruturada da execução. Ele gera primeiro um retrato preliminar para revisão, incorpora a revisão humana e gera um novo retrato identificado. O facilitador confere a gravação e abre o arquivo. Se o agente não puder escrever no Drive, ele fornece o conteúdo e o facilitador salva; não se declara atualização concluída antes de verificar o arquivo.

## Preparação

1. O facilitador escolhe um identificador novo, por exemplo `EX-001`, e registra `SA-ENCHENTE-01` e as pessoas/papéis no canal.
2. Prepara quatro arquivos CSV por lote a partir de `03-comunicacoes.csv`, preservando cabeçalho e linhas: `lote-1.csv` (20), `lote-2.csv` (25), `lote-3.csv` (20) e `lote-4.csv` (15). São cópias; o original permanece intacto.
3. Disponibiliza **somente o lote corrente** aos agentes. Se o CSV integral no Drive continuar acessível, não existe isolamento técnico de acontecimentos futuros: usar cópias controladas ou informar a limitação e não alegar teste cego. Uma instrução para ignorar os outros lotes não é bloqueio.
4. Define um local da execução no Drive para o estado e o `dashboard.html`; confirma como os agentes leem e gravam. Se não houver permissão, usa a alternativa manual abaixo.
5. Verifica se os quatro agentes conseguem ser chamados. A Coordenação já consultou Bombeiros e PM no teste de dois registros; a retomada após respostas assíncronas, a participação de outras pessoas e a Polícia Científica ainda precisam de teste completo.

## Rotinas existentes — fora do fluxo atual

| Rotina | Agente | Gatilho e entrega | Estado observado |
|---|---|---|---|
| Santa Aurora — coordenação por lote | Coordenação | Webhook → #santa-aurora | Pausada, ainda não rodou |
| Santa Aurora — análise Bombeiros | Bombeiros | Webhook → #santa-aurora | Pausada, ainda não rodou |
| Santa Aurora — análise PM | PM | Webhook → #santa-aurora | Pausada, ainda não rodou |
| Santa Aurora — análise pericial | Polícia Científica | Webhook → #santa-aurora | Pausada, ainda não rodou |

Esses gatilhos ainda são independentes: não há evidência de encadeamento automático, controlador de execução, entrega de payload ou atualização automática do Drive. Cada rotina foi criada ativa e pausada em seguida; a interface indicou que nenhuma havia sido executada. Não é necessário apagá-las. O fluxo direto por mensagem não usa seus webhooks; caso algum dia sejam ativadas, será necessário decidir como controlar acesso e entrega do lote e testar permissões e aprovações.

## Ciclo de execução

| Passo | Autor | Entrada e ação | Saída / condição de avanço |
|---|---|---|---|
| 1. Liberar | Facilitador | Disponibiliza lote seguinte e anuncia IDs de ocorrência, execução e lote. | Lote disponível; original preservado. |
| 2. Ler e extrair | Coordenação | Lê CSV com parser, preserva fonte e horário, propõe categorias, incidentes e pendências. | Lista com IDs e trechos; falha ou linha ilegível fica pendente. |
| 3. Consultar | Coordenação | Envia recortes e perguntas aos três especialistas conforme pertinência. | Respostas identificadas ou `aguardando`; nenhuma resposta presumida. |
| 4. Analisar | Agentes das forças | Identificam fatos relatados, lacunas e dependências; consultam outro especialista quando necessário. | Respostas com fontes e perguntas ao humano. |
| 5. Painel preliminar | Coordenação | Consolida respostas disponíveis e gera HTML marcado PRELIMINAR / AGUARDANDO REVISÃO. | Facilitador verifica arquivo, versão, fontes, lacunas e respostas aguardadas; falhas são registradas. |
| 6. Revisar e atualizar | Representantes humanos e Coordenação | Delacyr examina o HTML, informa decisões no canal; Coordenação preserva histórico e gera versão revisada. | Registro de autor, horário, decisão e fontes; confirmação da nova gravação. |
| 7. Prosseguir | Facilitador | Verifica pendências e libera próximo lote. | Repete até lote 4; encerramento só após revisão humana. |

Consultas podem ser assíncronas e uma conversa automática tem limites: o coordenador não deve esperar indefinidamente nem inventar resposta. Se a configuração pessoal impedir consulta direta, o facilitador encaminha a pergunta ao especialista e devolve **a resposta efetiva**, identificando o repasse manual.

## Mensagens e instruções para a execução futura

Os textos abaixo orientam o fluxo direto por mensagem, sem criar itens no quadro Tarefas nem executar as rotinas pausadas.

**A. Facilitador → Coordenação, em cada lote**

```text
@coordenacao Inicie/continue a simulação fictícia. Ocorrência SA-ENCHENTE-01;
execução EX-001; lote liberado [N]; entrada [nome ou link do lote]. Leia
apenas essa entrada e o estado confirmado da execução. Valide o CSV e extraia
propostas por comunicação com IDs, fonte, trecho e horário. Identifique
lacunas, possíveis duplicidades e divergências sem resolvê-las. Consulte
@bombeiros, @pm e @policiacientifica nas questões pertinentes; apresente
respostas recebidas e pendências. Gere dashboard.html preliminar no Drive,
marcado AGUARDANDO REVISÃO, com fontes, dúvidas e respostas aguardadas.
Informe o local e aguarde minha revisão antes de marcar informações confirmadas.
```

**B. Coordenação → cada especialista, ou facilitador por repasse manual**

```text
Ocorrência SA-ENCHENTE-01; execução EX-001; lote [N]. Examine os trechos
[IDs e texto]. Na sua especialidade, informe achados com fonte e horário,
o que está relatado ou contestado, e perguntas ao representante humano.
Consulte [outro especialista] somente se houver dependência concreta.
Não infira fatos ausentes nem execute medidas operacionais.
```

**C. Representante humano → canal**

```text
REVISÃO | ocorrência: SA-ENCHENTE-01 | execução: EX-001 | lote: [N]
Papel: [PM/Bombeiros/Polícia Científica/Coordenação] | Autor: [participante]
Registro ou comunicação: [ID] | Ação: [confirmar/corrigir/rejeitar/manter pendente]
Conteúdo e justificativa: [...] | Referências: [...] | Horário: [...]
```

**D. Coordenador humano → Coordenação**

```text
@coordenacao Considere as revisões humanas registradas até agora para
SA-ENCHENTE-01 / EX-001 / lote [N]. Preserve histórico, identifique itens
afetados e solicite reavaliação quando necessário. Gere uma nova versão dos
dados e do dashboard.html no Drive da execução, conforme o documento
06-dashboard.md. Informe local, versão, horário, fontes e falhas; se não
conseguir gravar, entregue os arquivos para o facilitador salvar.
```

## Reinício e recorrência

Para reiniciar, criar novo `execucao_id`, nova área de saída e estado vazio; registrar a liberação dos lotes novamente. Conservar a execução anterior e não reutilizar conclusões como evidência. Para uma nova ocorrência, atribuir outro `ocorrencia_id`; rejeitar associações entre ocorrências. A carga atual contém somente uma ocorrência, portanto isolamento real entre duas ainda precisa de teste com dados adicionais.

## Situação de conclusão

As instruções ativas da Coordenação foram alteradas para gerar painel preliminar antes da revisão. Leitura de dois registros e consulta direta foram demonstradas parcialmente; a geração e abertura do HTML e o ciclo completo ainda não foram testados. As rotinas seguem pausadas na última verificação e não são necessárias ao teste direto. O CSV integral não oferece isolamento técnico dos demais lotes. Itens no quadro Tarefas foram criados por engano; sua situação atual não foi verificada.
