# SEJUSP Integra

Projeto de simulação para apoiar a integração de informações entre Polícia Militar, Corpo de Bombeiros e Polícia Científica. O cenário é uma enchente fictícia em Santa Aurora (MS), com comunicações recebidas em momentos diferentes e necessidade de revisão humana. Todo o material da simulação é fictício e não deve ser usado como orientação operacional.

## Objetivo da apresentação final

Demonstrar o problema de informações dispersas, o fluxo proposto de colaboração entre agentes e pessoas, e o papel do dashboard na visualização de fontes, pendências e divergências. Diferenciar o que foi efetivamente demonstrado do que ainda é proposta ou depende de validação.

## Atividades a executar

### 1. Elaborar a apresentação

- [ ] Revisar os documentos do repositório e alinhar a narrativa entre os participantes.
- [ ] Apresentar o cenário de Santa Aurora, o problema de coordenação e o impacto pretendido para as pessoas afetadas.
- [ ] Explicar os papéis da Coordenação, dos agentes especialistas e dos representantes humanos, incluindo a revisão das informações antes de considerá-las confirmadas.
- [ ] Descrever a carga de 80 comunicações fictícias, dividida em quatro lotes, e ilustrar como fontes, horários, pendências e divergências são preservados.
- [ ] Mostrar o fluxo da simulação e o dashboard com evidências da execução, indicando eventuais passos manuais e limitações observadas.
- [ ] Encerrar com resultados demonstrados, pontos ainda não validados e próximos passos; ensaiar o tempo e a transição entre apresentadores.

**Entregável:** apresentação final e roteiro de fala, com referências aos documentos e às evidências utilizadas.

### 2. Capturar imagens e vídeos da ferramenta funcionando

- [ ] Preparar uma execução identificada e disponibilizar apenas o lote corrente aos agentes, conforme o roteiro; preservar o CSV original.
- [ ] Registrar a chamada da Coordenação, a leitura das comunicações e as consultas e respostas efetivamente recebidas dos especialistas.
- [ ] Capturar o dashboard preliminar, suas fontes e pendências e, se o ciclo for concluído, a revisão humana e a versão revisada.
- [ ] Conferir se as imagens estão legíveis, identificadas como simulação e livres de informações pessoais ou credenciais expostas.
- [ ] Editar um vídeo curto para a apresentação, preservando a ordem dos acontecimentos; identificar cortes, repasses manuais e falhas relevantes. Guardar também os registros originais.

**Entregável:** conjunto de imagens e vídeo demonstrativo, identificados por execução, lote e etapa. Se uma etapa não funcionar, registrar a limitação em vez de apresentá-la como concluída.

### 3. Refinar e melhorar o dashboard

- [ ] Criar e abrir o `dashboard.html` a partir do estado da execução, conforme a especificação; verificar o mecanismo de gravação no Drive ou utilizar o salvamento manual previsto.
- [ ] Melhorar a clareza visual e a navegação das seções de resumo, incidentes, pendências, divergências, linha do tempo e fontes.
- [ ] Exibir identificação da ocorrência e execução, lote, versão, horário de geração e aviso **SIMULAÇÃO — NÃO OPERACIONAL**; marcar o retrato preliminar como aguardando revisão.
- [ ] Tornar visíveis os estados das afirmações, as respostas aguardadas e as falhas, sem transformar relatos ou confirmações simuladas em revisão humana.
- [ ] Conferir IDs, trechos e horários contra as comunicações; manter divergências e histórico de revisões e evitar dados de lotes ainda não liberados.
- [ ] Testar abertura, legibilidade e atualização após uma revisão humana; registrar falhas e ajustes necessários. Para testar isolamento entre ocorrências, preparar uma segunda carga fictícia.

**Entregável:** dashboard demonstrável e registro dos testes realizados, limitações e melhorias pendentes. Os critérios detalhados estão em [06-dashboard.md](06-dashboard.md).

## Sequência sugerida

1. Preparar e executar a simulação, registrando as evidências disponíveis.
2. Refinar o dashboard e verificar os critérios aplicáveis com os dados da execução.
3. Selecionar as capturas, montar a apresentação e ensaiar a demonstração, mantendo uma alternativa gravada para eventuais falhas.

## Situação e limitações conhecidas

Conforme o registro em [05-tarefas-e-roteiro.md](05-tarefas-e-roteiro.md), houve demonstração parcial da leitura de dois registros e de consultas diretas. A geração e abertura do HTML, a consolidação após respostas assíncronas e o ciclo completo de revisão ainda não foram comprovados. As rotinas existentes estavam pausadas na última verificação e não fazem parte do fluxo direto proposto. O dashboard está especificado, mas sua criação e seus critérios de aceite ainda precisam ser verificados. A atualização proposta ocorre por regeneração do arquivo, não em tempo real.

## Materiais do repositório

- [Cenário piloto](01-cenario-piloto.md): contexto, problema e participantes.
- [Processo e dados](02-processo-e-dados.md): definições para tratamento das informações.
- [Carga fictícia](03-carga-ficticia.md) e [comunicações](03-comunicacoes.csv): descrição e dados da simulação.
- [Instruções dos agentes](04-instrucoes-dos-agentes.md) e [pesquisa de conhecimento](04-pesquisa-conhecimento.md): orientações e referências.
- [Fluxo e roteiro da simulação](05-tarefas-e-roteiro.md): preparação, execução e revisão humana.
- [Especificação do dashboard](06-dashboard.md): conteúdo, atualização e critérios de aceite.
