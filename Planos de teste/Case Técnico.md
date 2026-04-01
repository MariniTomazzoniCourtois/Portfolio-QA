# **\[Case Técnico\] QA Analyst – Qualidade e Automação de Software**

# **Contexto**

Você está assumindo o papel de QA Analyst em um dos produtos digitais da empresa XXX, um ecossistema de tecnologia voltado para XXX.

Uma nova funcionalidade será lançada em **5 dias úteis**:

**Sistema XXXXXXXXX XXXXXX.**

A funcionalidade inclui:

* Formulário de captura de leads (Frontend)

* API interna de processamento

* Integração com CRM externo

* Automação de envio de e-mails

* Dashboard de acompanhamento de leads

O desenvolvimento já está em andamento, porém ainda não existe uma estratégia formal de qualidade definida.

Seu papel é estruturar rapidamente o processo de QA para garantir um lançamento seguro, previsível e com o menor risco possível.

# **Desafio**

Atualmente o projeto apresenta os seguintes pontos pendentes:

* Não há critérios de aceite formalizados

* Não existem casos de teste documentados

* Testes estão sendo realizados apenas manualmente pelos desenvolvedores

* Integrações via API ainda não foram validadas

* Bugs são reportados informalmente

* Não há plano de regressão definido

* Não existe automação de testes

* Não há métricas ou acompanhamento de qualidade

O lançamento está previsto para **D+5 dias úteis**.

1. # **Prioridades nos primeiros 2 dias**

Quais seriam suas **3 a 5 ações imediatas** para colocar a qualidade do projeto sob controle? Considere:

* análise de riscos

  * organização inicial de QA

  * definição mínima necessária para validar o release

2. # **Estratégia de Testes**

Explique como estruturaria a estratégia de testes para essa entrega. Inclua:

* Tipos de testes aplicados:

  * Smoke Test

    * Testes Funcionais

    * Testes Exploratórios

    * Testes de Regressão

    * Testes de Integração

    * Testes de API

  * Técnicas de design de teste que utilizaria:

    * Particionamento de equivalência

    * Análise de valor limite

    * Tabela de decisão

    * Teste baseado em estado

Descreva brevemente **quando e por que** aplicaria cada abordagem.

3. # **Automação e Redução de Testes Manuais**

Hoje o processo é totalmente manual. Explique:

* O que você automatizaria primeiro e por quê

  * Como aplicaria o conceito da **Pirâmide de Testes**

  * Que tipos de testes ficariam em:

    * nível unitário

    * nível de API

    * nível end-to-end (E2E)

Descreva também como iniciaria uma estratégia de automação mesmo com prazo curto.

4. # **Testes de API e Integrações**

A funcionalidade depende da integração com um CRM externo. Explique:

* Como validaria os endpoints utilizando Postman

  * Quais validações executaria (status code, payload, autenticação, schema)

  * Como organizaria collections e environments

  * Como reutilizaria esses testes no futuro

5. # **Gestão de Bugs e Evidências**

Descreva como estruturaria o processo de qualidade relacionado a bugs:

* Como registrar bugs de forma clara

  * Evidências necessárias (logs, prints, passos)

  * Workflow ideal do bug até validação final

  * Como reduzir retrabalho entre QA e desenvolvimento

6. # **Comunicação e Cultura de Qualidade**

Explique como atuaria dentro de um ambiente ágil para garantir qualidade desde o início:

* Participação em refinamentos e plannings

  * Definição de critérios de aceite

  * Antecipação de riscos

  * Colaboração com desenvolvedores

7. # **Ferramentas**

Quais ferramentas utilizaria para organizar o fluxo de QA? Considere:

* gestão de tarefas/testes

  * execução de testes API

  * automação

  * documentação

  * acompanhamento de métricas

Explique brevemente o motivo das escolhas.

# **Diferencial (Opcional)**

Descreva quais melhorias você implementaria nos próximos **90 dias** para evoluir o time de QA de um modelo manual para uma cultura de **Quality Engineering**, incluindo possíveis iniciativas de:

* automação contínua

  * CI/CD

  * métricas de qualidade

  * boas práticas (Shift Left Testing, Pirâmide de Testes)
