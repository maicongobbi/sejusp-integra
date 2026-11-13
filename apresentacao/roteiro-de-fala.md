# Roteiro de fala — SEJUSP Integra

Apresentação: [index.html](index.html) (tecla **N** mostra este roteiro durante a apresentação). Tempo total estimado: 17–19 min.

> Todas as telas marcadas “Ilustração · tela simulada” mostram o comportamento esperado do fluxo; a única captura real está no slide 14. Material inteiramente fictício.

## 1. Capa

![](imagens/01-capa.png)

**Abertura (≈40 s).** Apresentar o SEJUSP Integra como um exercício: não é um sistema em produção. A proposta é mostrar como agentes de IA e profissionais de três forças podem tratar juntos um grande volume de comunicações, sem que a IA decida nada. Reforçar logo de início: todo o material é fictício e não serve como orientação operacional.

## 2. Cenário

![](imagens/02-cenario.png)

**Cenário (≈1 min).** Santa Aurora é fictícia. Mostrar no mapa os pontos que vão reaparecer na apresentação: a escola, a Rua das Flores, a ponte, o motorista na avenida, a Rua Ipê, a Rua Palmeiras e a Rua Cedro. A escola concentra o apelo emocional, mas o exercício também cobre os bairros.

## 3. Problema

![](imagens/03-problema.png)

**Problema (≈1 min).** A dor não é falta de informação, é a informação dispersa: o pedido, a restrição de acesso e o atendimento em andamento estão em lugares diferentes. Ler a fala da responsável: ela precisa que alguém diferencie boato, informação da escola e atualização de equipe. Esse é o impacto humano pretendido — reduzir perdas de informação. É uma hipótese; não afirmamos que o tempo de socorro diminui.

## 4. AS-IS → TO-BE

![](imagens/04-as-is-to-be.png)

**Processo (≈1 min).** À esquerda, o fluxo assumido para a oficina — deixar claro que não levantamos o processo real. À direita, a proposta: tudo vira registro rastreável, a IA propõe, os especialistas cruzam informações, o painel mostra lacunas e o humano decide.

## 5. REGRA · LLM · HUMANO

![](imagens/05-regra-llm-humano.png)

**Divisão de papéis (≈1 min).** Esta é a ideia central da aula aplicada ao caso. As etiquetas descrevem responsabilidades, não funcionalidades já implementadas. Destacar: a IA nunca soma contagens, nunca une registros sozinha e nunca declara rota segura, óbito ou identidade.

## 6. Participantes

![](imagens/06-participantes.png)

**Participantes (≈1 min).** Os quatro agentes foram criados no workspace e estão no canal #santa-aurora. A Coordenação é a interlocutora e a única que escreve o painel — isso evita sobrescrita concorrente. As três especialidades se justificam pelas dependências entre acesso, salvamento e perícia; isso é uma hipótese de arquitetura a comparar com um agente único. Com três pessoas, os papéis humanos podem ser acumulados.

## 7. Carga fictícia

![](imagens/07-carga-ficticia.png)

**Carga (≈1 min 30).** 80 mensagens, quatro lotes, alguns horas de ocorrência simulada. Não existe gabarito: o objetivo é ver se o sistema preserva as dificuldades em vez de “resolvê-las” sozinho. Passar rapidamente pela tabela — cada linha é um teste do comportamento esperado. Lembrar que a versão enriquecida do CSV (revisão 2, ~62 palavras por mensagem) ainda precisa ser versionada no Drive antes de nova execução.

## 8. Comunicação → afirmação

![](imagens/08-comunicacao-afirmacao.png)

**Rastreabilidade (≈1 min).** Exemplo concreto com a primeira mensagem do CSV. A moradora diz que há crianças, mas não sabe quantas: a quantidade fica nula, não zero. O que ela não verificou vira pendência para a PM. Cada afirmação carrega o ID e o trecho de origem. Os quatro estados de verificação aparecem em todo o painel.

## 9. Tela: canal

![](imagens/09-tela-canal.png)

**Tela do canal (≈1 min 30).** Esta tela é uma ilustração montada a partir do roteiro, não uma captura. Mostra os passos 1 a 5: o facilitador libera o lote com ocorrência, execução e lote explícitos; a Coordenação lê, propõe incidentes e consulta especialistas; os especialistas respondem com ID e trecho; a Coordenação publica o painel preliminar. Na execução real, a leitura de dois registros e consultas diretas a Bombeiros e PM já foram observadas.

## 10. Tela: dashboard preliminar

![](imagens/10-tela-dashboard-preliminar.png)

**Dashboard preliminar (≈1 min 30).** Também é uma ilustração, construída a partir da especificação 06-dashboard.md. Apontar os elementos obrigatórios: faixa SIMULAÇÃO — NÃO OPERACIONAL; ocorrência, execução, lote, versão e horário de geração; o aviso de PRELIMINAR; os indicadores contam registros, nunca pessoas. A relação com a “casa azul” aparece como proposta, não como união. A mensagem que manda ignorar as regras aparece sinalizada, mas não foi obedecida. O painel é um retrato: só muda quando é regenerado.

## 11. Tela: divergências e pendências

![](imagens/11-tela-divergencias-e-pendencias.png)

**Divergências e pendências (≈1 min 30).** O ponto mais sensível do cenário: a Rua Cedro tem uma confirmação simulada de um óbito e um boato de dois. O sistema não soma nem escolhe — mostra os dois lados com fonte e horário. Na correção da PM, a informação antiga não é apagada: fica como desatualizada e os itens que dependiam dela são marcados para reavaliação. Na fila de pendências, cada questão tem um responsável sugerido e um estado — inclusive “aguardando”, quando a consulta não teve resposta.

## 12. Tela: revisão humana

![](imagens/12-tela-revisao-humana.png)

**Revisão humana (≈1 min).** As pessoas registram decisões no canal num formato padronizado: ocorrência, execução, lote, papel, ação, justificativa e referências. A Coordenação incorpora as decisões e gera uma nova versão. Repare: “confirmado” agora traz autor e hora humanos; o “eram 20” continua visível; a versão anterior é preservada. Importante: o ciclo completo de revisão ainda não foi comprovado na execução real — esta tela mostra o comportamento esperado.

## 13. Ciclo por lote

![](imagens/13-ciclo-por-lote.png)

**Ciclo (≈45 s).** Recapitular os sete passos. Os três cartões de baixo são as salvaguardas que tornam o fluxo honesto: não esperar indefinidamente, registrar repasses manuais e deixar claro que o painel não se atualiza sozinho.

## 14. Evidências e situação

![](imagens/14-evidencias-e-situacao.png)

**Evidências (≈1 min 30).** Este é o slide da honestidade. À esquerda, a única captura real: a Coordenação compartilhou o dashboard.html versão 4 da execução DEMO-001, marcado como parcialmente revisado, depois de conversar com Bombeiros e PM. Ressaltar que essa execução usou o CSV antigo. À direita, a separação entre o que observamos, o que foi parcial e o que ainda é proposta. As telas anteriores mostram o comportamento esperado do fluxo completo. Se houver vídeo da execução, exibir aqui.

## 15. Riscos

![](imagens/15-riscos.png)

**Riscos (≈45 s).** A classificação é didática. O risco mais grave é transformar relato em fato; quase todos os controles do desenho existem para impedir isso. Uma implantação real exigiria avaliação própria do órgão.

## 16. Próximos passos

![](imagens/16-proximos-passos.png)

**Próximos passos (≈1 min).** Ser concreto: o que falta é rodar o ciclo inteiro com a carga revisada e medir. O ganho de tempo é uma hipótese a medir, não uma conclusão. Terminar com o que já se pode afirmar com base nas evidências.

## 17. O sistema em uma imagem

![](imagens/17-o-sistema-em-uma-imagem.png)

**Fechamento (≈45 s).** Uma imagem para resumir: comunicações entram em lotes controlados; a Coordenação organiza e consulta especialistas; o painel mostra relatos, divergências e lacunas; e as pessoas decidem, gerando uma nova versão. A IA organiza; quem confirma é sempre um profissional. Abrir para perguntas.
