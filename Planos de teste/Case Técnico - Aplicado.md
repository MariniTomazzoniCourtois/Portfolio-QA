[Case técnico QA - Marini.md](https://github.com/user-attachments/files/26421596/Case.tecnico.QA.-.Marini.md)
# **\[Case Técnico\] QA Analyst – Qualidade e Automação de Software**

# **Contexto**

Você está assumindo o papel de QA Analyst em um dos produtos digitais da Atomic Group, um ecossistema de educação e tecnologia voltado para aceleração de receita empresarial.

Uma nova funcionalidade será lançada em **5 dias úteis**:

#### **Sistema de Captura e Gestão de Leads integrado ao CRM e automação de comunicação.**

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

# **Instruções para o Case (Entregável)**

Você deverá apresentar um plano simples (texto, slide ou PDF) respondendo aos pontos abaixo:

1. # **Prioridades nos primeiros 2 dias**

Nos 2 primeiros dias o foco é entender o fluxo do sistema, identificar riscos e definir o mínimo necessário para garantir uma validação segura do release.

#### **Dia 1 \- Foco em entender o fluxo do sistema, organizar QA e definir critérios de aceite Análise de riscos:**

- Alinhamento com os devs para mapear o fluxo completo (frontend, API, CRM, e-mail,

  dashboard) mapeando dados, endpoints, funcionamento da integração com CRM, tipos de e-mail e informações exibidas no dashboard

  - Identificar fluxos críticos e riscos do sistema (EX.: Falha na integração com CRM, Não envio de e-mails, Inconsistência de dados)

  - Checklist de smoke tests de API, Frontend, Integração, Envio de e-mails

**Organização inicial de QA:**

- Alinhamento com devs para entender regras de negócio  
  - Definir padrão de bugs (título, descrição, prioridade, passo a passo, resultado esperado vs atual, evidências)  
  - Preparar ferramentas para testes  
  - Priorizar testes com base no impacto

#### **Definição mínima para validar o release:**

Definição de critérios de aceite mínimos. A release não avança caso falhem. Portanto:

- **Formulário funcionando**: O formulário deve permitir envio de leads com dados válidos e retornar confirmação de sucesso

  - **API interna correta:** A API deve processar os dados do lead corretamente, aplicando as regras de negócio e retornando respostas adequadas

  - **CRM recebendo leads:** Os leads criados no sistema devem ser enviados e registrados corretamente no CRM

  - **Automação de envio de emails:** O sistema deve disparar os e-mails configurados para o lead após sua criação

  - **Dashboard de acompanhamento de leads:** O dashboard deve exibir os dados dos leads corretamente

#### **Dia 2 \- Começo de smoke tests e cenários críticos**

- Smoke tests de Frontend, API, integração com CRM, envio de e-mails  
  - Criação e execução de testes: cenários críticos, CRUD, Aplicando: Particionamento de equivalência e Análise de valor limite.  
  - Registros de bugs encontrados  
  - Alinhamento contínuo com devs, apoio na reprodução de bugs

Com os dois primeiros dias estruturados, os próximos dias seriam focar na expansão da cobertura de testes, validação de integrações, teste de regressão e garantia da estabilidade do sistema:  
No 3º dia o foco é garantir o funcionamento de fluxos críticos e realizar o reteste de bugs corrigidos.

No 4º dia o foco é nas integrações do sistema, com testes de API, execução de cenários positivos e negativos e conforme o tempo disponível, testes exploratórios.  
No 5º e último dia, o foco é garantir a estabilidade do sistema, com execução de teste de regressão nos principais fluxos, como criação de lead pelo formulário, integração com CRM, envio de e-mails e visualização de dados no dashboard, além da verificação final de pendências de bugs antes da entrega.

2. # **Estratégia de Testes**

A estratégia de testes será focada nos fluxos críticos do sistema, priorizando validações que garantam o funcionamento da captura e processamento de leads.

## Tipos de testes aplicado:

### **Smoke Test**

**Quando**: Início dos testes, a cada atualização relevante (correção de bug), antes da regressão e antes da entrega da release.  
**Porque:** Smoke tests devem ser executados ao longo de todo o ciclo de teste porque podem identificar falhas críticas, o que evita desperdício de tempo.

### **Testes Funcionais**

**Quando**: Após smoke test e conforme novas entregas  
**Porque:** Com o sistema estável é possível validar regras de negócios e critérios de aceite.

### **Testes Exploratórios**

**Quando**: Após os testes funcionais  
**Porque:** São utilizados para identificar falhas não previstas, sendo aplicados conforme disponibilidade de tempo.

### **Testes de Regressão**

**Quando**: As primeiras funcionalidades estiverem estáveis (Formulário, API interna), depois que todas estiverem estáveis  
**Porque:** Garantir que novas alterações não quebraram o que já funciona.

### **Testes de Integração**

**Quando**: Quando CRM e serviço de e-mail estiverem disponíveis.  
**Porque:** Garantir que os sistemas se comunicam corretamente (API interna \+ CRM \+ automação).

### **Testes de API**

**Quando**: Início do projeto como smoke tests e após integração  
**Porque:** Para validar se os endpoints estão funcionando e garantir a estabilidade das integrações.

## Técnicas de design de teste que utilizaria:

### **Particionamento de equivalência**

**Quando**: Formulário e entrada de dados  
**Porque:** Reduz o número de cenários e mantém cobertura.

### **Análise de valor limite**

**Quando**: Em campos com restrições

**Porque**: erros geralmente ocorrem nos limites (máximo/mínimo de caracteres, tamanho de campos), o que aumenta a chance de encontrar bugs com poucos testes.

### **Tabela de decisão**

**Quando**: Fluxo com regras, como automação de email.  
**Porque:** Garante uma cobertura completa de combinações de regras

### **Teste baseado em estado**

**Quando**: Fluxos onde o sistema muda de estado (ex: lead criado \> processado \> enviado ao CRM \> convertido)  
**Porque:** Para validar que as transições de estado acontecem na ordem correta

3. # **Automação e Redução de Testes Manuais**

Iniciaria a automação pelos testes de API (criação de lead, validação de payload, status code e autenticação), pois são mais rápidos de implementar e cobrem grande parte das regras de negócio e integrações (CRM e envio de e-mails).

* Como aplicaria o conceito da **Pirâmide de Testes**

  Na base da pirâmide, os desenvolvedores serão responsáveis pelos testes unitários, garantindo qualidade desde o código.

  Na camada intermediária, o QA atua com foco principal em testes de API, pois oferecem maior cobertura das regras de negócio e integrações com menor custo e maior estabilidade.

  No topo, os testes E2E também ficam sob responsabilidade do QA, sendo utilizados em menor quantidade para validar os fluxos críticos do sistema.

* Que tipos de testes ficariam em:

  * nível unitário:  
    - Validações de entrada (campos obrigatórios, formato de e-mail, limite de dados)  
    - Regras de negócio (condições, decisões)  
    - Tratamento de erros e exceções (comportamento da API quando recebe dados incorretos)

  * nível de API:  
    - Validação de endpoints (status code, payload, autenticação)  
    - Regras de negócio via API  
    - Integrações com CRM e serviços de e-mail  
    - Consistência de dados entre sistemas

  * nível end-to-end (E2E):  
    - Fluxos críticos do sistema: criação de leads, processamento via API, integração com CRM, envio de e-mails e visualização no dashboard.

#### **Descreva também como iniciaria uma estratégia de automação mesmo com prazo curto:**

Começaria com Postman para automação de API, utilizando scripts básicos e execução via Collection Runner. Em seguida, iniciaria a estrutura de testes E2E com Playwright para cobrir fluxos críticos, evoluindo gradualmente.

4. # **Testes de API e Integrações**

* #### **Como validaria os endpoints utilizando Postman**

Utilizaria o Postman para executar requisições e validar os endpoints principais, como criação e consulta de leads, organizando os testes por fluxo de negócio, cobrindo cenários positivos e negativos.

**Quais validações executaria (status code, payload, autenticação, schema)** Utilizo a heurística VADER como guia para garantir cobertura dos principais pontos: **V – Verbos:** validação de métodos HTTP permitidos  
**A – Autenticação:** validação de acesso (401, 403\)

**D – Dados:** validação de payload e schema

**E – Erros:** validação de respostas de erro (400, 404, 500\)

**R – Responsividade:** tempo de resposta da API

* #### **Como organizaria collections e environments**

- Collections serão separadas por funcionalidade: Leads API, Integração CRM, Automação de e-mail.  
- Environments serão utilizados para separar configurações entre ambientes (Dev e Staging), utilizando variáveis como base\_url, token e lead\_id. Isso facilita a execução dos mesmos testes em diferentes ambientes, reduz erros e evita retrabalho.

* #### C**omo reutilizaria esses testes no futuro**

- As collections podem ser executadas via Collection Runner, permitindo validações frequentes durante o desenvolvimento. Futuramente, podem ser integradas ao CI/CD para automação contínua dos testes.

5. # **Gestão de Bugs e Evidências**

Os bugs serão registrados com:

- **Título**  
  - **Descrição**  
  - **Tipo:** (Correção, Melhoria, Nova funcionalidade)  
  - **Prioridade**: (Alta, Média, Baixa)  
  - **Passo a passo**  
  - **Resultado esperado vs atual**  
  - **Evidências**

* #### **Evidências necessárias (logs, prints, passos)**

  - Prints/vídeos  
  - Payload da requisição  
  - Resposta da API

* #### **Workflow ideal do bug até validação final**

  - QA abre bug \> To Do  
  - Dev corrige \>In Progress  
  - QA valida \>In Test  
  - Finalizado \> Done

* Como reduzir retrabalho entre QA e desenvolvimento

  - Validar previamente com dev se é um bug

  - Registrar bug de forma clara

  - Manter comunicação contínua com o time

6. # **Comunicação e Cultura de Qualidade**

O QA vai atuar de forma contínua e colaborativa ao longo de todo o ciclo de desenvolvimento, reforçando o conceito de Shift Left, promovendo a prevenção de falhas e a responsabilidade compartilhada pela qualidade.

* #### **Participação em refinamentos e plannings**

  Participação ativa do QA para entender as demandas, esclarecer dúvidas, identificar possíveis riscos antes do desenvolvimento.

* #### **Definição de critérios de aceite**

  São definidos de forma clara e objetiva junto ao time, servindo como base para a validação de fluxo principal, cenários alternativos e erros.

* #### **Antecipação de riscos**

  QA identifica cenários críticos, possíveis falhas de integração e pontos de atenção, a fim de priorizar os testes com base no maior impacto.

* #### **Colaboração com desenvolvedores**

  QA atua próximo aos desenvolvedores, tratando a qualidade como responsabilidade do time.

7. # **Ferramentas**

Quais ferramentas utilizaria para organizar o fluxo de QA?

* #### **gestão de tarefas/testes**

  - **Azure DevOps**

  **Motivo:** Ferramenta de fácil entendimento, permite gerenciar todo o ciclo de vida da aplicação. Organiza tarefas, bugs e fluxo de desenvolvimento em um único lugar, facilitando o acompanhamento do progresso do time.

* #### **execução de testes API**

  - **Postman**

  **Motivo:** Ferramenta prática para criação e execução de testes de API, permitindo validar endpoints, status code, payloads e autenticação de forma rápida, possibilitando automações básicas.

* #### **automação**

  - **Postman \+ Playwright**

  **Motivo:** Postman para automação de testes de API, endpoints, regras de negócio e integrações com rapidez através de scripts e execução via Collection Runner.

  Playwright para testes end-to-end, que após pesquisa, foi concluído que é uma ferramenta estável para fluxos com múltiplas etapas. Possui suporte a diferentes navegadores (Chrome, Firefox e Safari), permite execução paralela, reduzindo o tempo de execução dos testes e permite simulação de serviços externos como CRM e envio de e-mails (recurso de mock), garantindo maior confiabilidade nos testes e melhor escalabilidade da automação a longo prazo.

* #### **documentação**

  - **Notion**

  **Motivo:** Ferramenta simples e colaborativa, permite centralizar informações e mantém a documentação acessível para todo o time.

* **acompanhamento de métricas**  
  - **Azure DevOps**

  **\-TestLink (alternativa)**

  **Motivo:** O Azure DevOps tem foco maior em acompanhamento geral do projeto, permite criar queries e dashboards para monitorar métricas como quantidade de bugs (abertos/fechados), status das tarefas, progresso das entregas e tempo de resolução, que ajudam a acompanhar a qualidade do produto e apoiar decisões.

  O TestLink tem foco maior em testes manuais. Pode ser utilizado como alternativa/complemento, para uma visão mais detalhada da execução dos testes, permitindo acompanhar métricas como taxa de sucesso e falha, cobertura por funcionalidade e evolução dos testes ao longo dos ciclos.

# **Diferencial (Opcional)**

Descreva quais melhorias você implementaria nos próximos **90 dias** para evoluir o time de QA de um modelo manual para uma cultura de **Quality Engineering**, incluindo possíveis iniciativas de:

* automação contínua

* CI/CD

* métricas de qualidade

* boas práticas (Shift Left Testing, Pirâmide de Testes)

Para implantar uma cultura de Quality Engineering, focaria em estruturação do processo, evolução da automação e tomada de decisão baseada em métricas.

No primeiro mês, estruturaria o processo de qualidade, organizando critérios de aceite, padronização de bugs e casos de teste, além de iniciar a automação de testes de API com Postman e buscar introduzir o QA desde o início do desenvolvimento, participando de refinamentos e reuniões (Shift Left).

No segundo mês, escalaria a automação, evoluindo os testes de API com execução contínua e integrando ao pipeline de CI/CD do AzureDevops, garantindo que os testes sejam executados automaticamente a cada nova alteração no código. Também iniciaria testes E2E com Playwright para cobrir os fluxos críticos do sistema.

No terceiro mês, focaria em métricas e melhoria contínua, acompanhando indicadores como quantidade de bugs, bugs em produção, tempo de resolução e cobertura de testes, utilizando esses dados para priorizar correções e direcionar ações de melhoria junto ao time.

Ao longo desse processo, aplicaria boas práticas como automação contínua (testes executados automaticamente a cada alteração), Shift Left (QA atuando desde o início para prevenção de falhas) e Pirâmide de Testes priorizando testes unitários na base, de responsabilidade dos desenvolvedores, garantindo qualidade desde o código, testes de API como principal foco do QA, cobrindo regras de negócio e integrações, e testes E2E voltados para validação dos fluxos críticos do sistema.

# **Critérios de Avaliação**

* Clareza e objetividade

* Capacidade de priorização

* Raciocínio técnico em QA

* Organização e visão prática de qualidade

* Conhecimento de testes e automação

* Comunicação técnica

* Mentalidade de melhoria contínua e postura de dono

# **Prazo para Entrega**

A definir pelo processo seletivo.

# **Observações**

Não buscamos respostas acadêmicas ou extensas, mas sim uma visão prática de como você organizaria a qualidade em um cenário real com prazo curto.
