# Pesquisa de conhecimento — SEJUSP Integra

**Data:** 13/11/2026. **Objetivo:** fundamentar os agentes do exercício de Santa Aurora. Fontes públicas oficiais e documentação primária da plataforma; não houve consulta a protocolos internos nem verificação da instalação. O exercício é fictício e suas regras não substituem procedimentos operacionais.

## Síntese por especialidade

| Especialidade | Conhecimento confirmado e aplicação didática | Limite |
|---|---|---|
| Coordenação | O [Ibama descreve o SCI](https://www.gov.br/ibama/pt-br/assuntos/fiscalizacao-e-protecao-ambiental/emergencias-ambientais/sci) como estrutura comum para coordenar pessoal, recursos, procedimentos e comunicações entre agências. O [Ministério da Integração](https://www.gov.br/mdr/pt-br/assuntos/protecao-e-defesa-civil/defesa-civil/como-se-organiza) descreve articulação entre entes e órgãos de proteção e defesa civil. Aplicação: identificar dependências, responsabilidades, fontes e pendências. | O protótipo é inspirado em coordenação integrada; não declara implementar SCI nem substitui comando humano. |
| Bombeiros | O [CBMMS lista busca e salvamento, atendimento pré-hospitalar e combate a incêndio](https://www.bombeiros.ms.gov.br/). Aplicação: organizar pedidos, pessoas relatadas, condições e atualizações de equipes, apontando informação ausente. | Não há cálculo de rota, técnica de resgate, triagem clínica ou despacho pela IA. |
| PM | Um [manual de defesa civil de Pernambuco](https://www.defesacivil.pe.gov.br/images/Manual/Manual_2019_final_tamanho_menor.pdf) exemplifica isolamento de áreas atingidas e apoio à segurança. Aplicação: registrar observações de bloqueio, local, fonte e horário, e consultar o profissional responsável. | O manual é de outro estado; não comprova protocolo local da PMMS. Via observada livre não é rota segura. |
| Polícia Científica | Os [procedimentos de medicina legal do MJSP](https://www.gov.br/mj/pt-br/assuntos/sua-seguranca/seguranca-publica/analise-e-pesquisa/pop/pops-pericia-criminal-2024-medicina-legal-vol-7-pdf.pdf) tratam de rastreabilidade e recomendam evitar atribuir identidades no local em múltiplas vítimas. Aplicação: distinguir relato, confirmação atribuída, solicitação e andamento pericial. | Não diagnosticar morte, identidade, causa, método de remoção ou cadeia de custódia; qualquer ação técnica é humana. |
| Dados e privacidade | A [ANPD discute proteção de dados em contextos de segurança pública](https://www.gov.br/anpd/pt-br/canais_atendimento/agente-de-tratamento/relatorio-de-impacto-a-protecao-de-dados-pessoais-ripd). Aplicação: usar apenas dados fictícios e minimizar detalhes no painel compartilhado. | O enquadramento legal de uso real depende da finalidade e de análise institucional; este material não é parecer jurídico. |

## Plataforma: evidências e questões em aberto

- O produto descreve agentes com papéis, ferramentas e responsáveis, e consultas privadas entre agentes. As consultas podem ser assíncronas; o limite padrão de três respostas consecutivas e a roteação do canal devem ser considerados. [Comunicação entre agentes](https://agentes.chat/pt/recursos/agentes-que-conversam-entre-si).
- A [wiki é lida pelos agentes](https://agentes.chat/pt/docs/wiki), podendo conter o bloco de conhecimento comum e o processo didático. O Agentes.chat possui computador e arquivos por agente, e conectores por MCP; a documentação não prova quais permissões ou conexões estão ativas no workspace do usuário. [Sobre](https://agentes.chat/pt/sobre).
- [Aprovações](https://agentes.chat/pt/docs/approvals) variam conforme ação e configuração. Testar gravação, revisão, histórico e publicação com arquivos de ensaio antes de depender do fluxo. A consulta entre agentes pode ocorrer em conversa privada; o coordenador deve registrar no canal um resumo rastreável, sem prometer que todas as mensagens estarão visíveis.
- **A testar na instalação:** localizar o CSV no Drive, leitura efetiva, isolamento dos lotes, escrita de HTML, abertura/renderização, persistência dos resultados e atualização. Nenhuma dessas operações foi executada ou confirmada nesta pesquisa. Se o Drive apenas baixar HTML, baixar e abrir localmente; não prometer atualização automática nem publicação.
- Entrada única indicada: `comunicacoes.csv` na pasta Drive, com o esquema de `03-comunicacoes.csv`. O nome e caminho exatos devem ser confirmados no workspace; não presumir que o arquivo local já tenha sido enviado. O arquivo completo expõe lotes futuros: limitar o acesso por cópias de lote ou ferramenta de liberação, não apenas por instrução textual.

## Decisões arquiteturais e fontes

Coordenador e três especialistas refletem as três instituições. A extração pode ser feita pelo coordenador com uma ferramenta de leitura/validação; gerar o dashboard também é tarefa do coordenador ou de ferramenta designada, sem exigir mais um agente. Isso é uma proposta do projeto, não um requisito das fontes. O coordenador aguarda respostas ou registra ausência; não inventa consultas realizadas.

Pesquisa focada em fontes oficiais disponíveis publicamente; não foi uma revisão sistemática nem validação com profissionais. Para uso real, complementar com protocolos locais, exercícios e avaliação institucional.
