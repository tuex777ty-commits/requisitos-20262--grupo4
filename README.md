[P1 — Sistema de Apoio ao ENADE (1).md](https://github.com/user-attachments/files/34292761/P1.Sistema.de.Apoio.ao.ENADE.1.md)
Trabalho P1 · Sprint 1 · M1

# Sistema de Apoio ao ENADE

Elicitação de requisitos, definição de escopo e modelagem UML inicial para sistema web/mobile de apoio à preparação para o ENADE.

Disciplina: Requisitos e Modelagem de Sistemas Prof. Bezerra — UNIFOR 02 nov 2026 Sprint 1 (20/10 – 02/11/2026)

## Índice

1. [Documento de Visão](#visao)
2. [Identificação de Stakeholders](#stakeholders)
3. [Roteiro e Resultados de Entrevistas](#entrevistas)
4. [Requisitos Funcionais](#rf)
5. [Requisitos Não Funcionais](#rnf)
6. [Regras de Negócio](#rn)
7. [Backlog Priorizado](#backlog)
8. [Diagrama de Casos de Uso](#uc)
9. [Diagrama de Componentes](#comp)
10. [Diagrama de Implantação](#impl)

1

## Documento de Visão

### Problema

Estudantes universitários que irão realizar o ENADE enfrentam dificuldades em sua preparação devido à ausência de uma plataforma centralizada que ofereça questões comentadas, simulados com condições reais de prova e análise de desempenho personalizada. O material disponível está disperso em fontes não oficiais, sem organização por curso, ano e componente curricular.

### Oportunidade

Desenvolver um sistema web/mobile que centralize questões oficiais do ENADE (portal INEP), ofereça gabarito comentado, simulados cronometrados e dashboard de desempenho, beneficiando estudantes, professores e coordenações de curso.

### Descrição do Sistema

O **ENADE+** é uma plataforma web e mobile de apoio à preparação para o ENADE, direcionada a estudantes de graduação do ensino superior brasileiro. O sistema permite acesso a um banco de questões organizado por ano, curso/área e componente (formação geral e conhecimento específico), com gabarito comentado, simulados cronometrados, estatísticas de desempenho e fórum colaborativo.

### Objetivos do Sistema

Centralizar questões

Banco de questões oficiais ENADE organizadas por ano, curso e componente curricular.

Simular o exame

Simulados com tempo cronometrado e condições semelhantes à prova real.

Apoiar o aprendizado

Gabarito comentado com explicações detalhadas de cada alternativa.

Monitorar desempenho

Dashboard com estatísticas por área de conhecimento e evolução ao longo do tempo.

### Escopo

O sistema **inclui**: banco de questões, simulados cronometrados, gabarito comentado, estatísticas de desempenho, fórum de discussão por questão, autenticação de estudantes e administradores.

O sistema **não inclui** (nesta fase): gamificação avançada, integração com sistemas acadêmicos da IES, geração automática de questões por IA, aplicativo nativo iOS/Android (somente PWA responsivo).

---

2

## Identificação de Stakeholders

| Stakeholder | Papel | Interesse | Influência | Tipo |
| --- | --- | --- | --- | --- |
| Estudante de graduação | Usuário principal | Preparação eficiente para o ENADE; feedback sobre desempenho | Alta | Direto |
| Professor | Usuário secundário / curador | Acompanhar evolução dos alunos; indicar material de estudo | Média | Direto |
| Coordenação de Curso | Gestor pedagógico | Monitorar desempenho coletivo; elevar nota do curso no ENADE | Alta | Direto |
| Administrador do Sistema | Operação e manutenção | Gerenciar questões, usuários e conteúdo da plataforma | Alta | Direto |
| INEP / MEC | Fonte de dados | Disponibilizar questões via portal público | Baixa | Indireto |
| Equipe de desenvolvimento | Construtora da solução | Requisitos claros e viáveis para implementação | Alta | Interno |
| Instituição de Ensino (UNIFOR) | Patrocinadora / beneficiária | Melhoria do índice ENADE; fortalecimento da imagem acadêmica | Média | Indireto |

---

3

## Roteiro e Resultados de Entrevistas

### Técnicas Utilizadas

Foram aplicadas entrevistas semiestruturadas com 5 estudantes de cursos distintos (Engenharia de Software, Direito, Administração, Medicina e Pedagogia) e um formulário online complementar (Google Forms) distribuído para 30 respondentes.

### Roteiro de Entrevista — Estudantes

1\. Você já utilizou alguma plataforma para estudar para o ENADE? Qual? O que faltava?

Maioria usou QConcursos ou o próprio site do INEP. Reclamações: falta de comentário nas respostas, interface confusa, ausência de simulados por curso específico.

2\. Qual recurso você considera mais importante para sua preparação?

Gabarito comentado (mencionado por 80% dos entrevistados) e simulado cronometrado (60%).

3\. Você prefere estudar no computador ou no celular?

Celular durante deslocamentos, computador para simulados completos. Sistema deve ser responsivo.

4\. Quão importante é poder ver seu histórico de desempenho?

Muito importante — 90% dos entrevistados querem saber quais áreas precisam de mais atenção.

5\. Você participaria de um fórum de discussão das questões?

Sim, desde que moderado. Interesse maior entre alunos de exatas e humanas.

### Principais Insights da Elicitação

Comentários são essenciais

100% dos entrevistados citaram gabarito comentado como requisito obrigatório, não diferencial.

Filtro por curso é crítico

Estudantes querem ver apenas questões do seu curso/área, especialmente no componente específico.

Acesso mobile é mandatório

Interface responsiva é indispensável; estudantes usam o celular em momentos livres do dia.

Dashboard motiva o estudo

Visualizar progresso e identificar pontos fracos aumenta o engajamento com a plataforma.

---

4

## Requisitos Funcionais

- RF01O sistema deve permitir cadastro e autenticação de estudantes com e-mail e senha.
- RF02O sistema deve permitir que o estudante filtre questões por ano de prova, curso/área e componente (formação geral ou conhecimento específico).
- RF03O sistema deve exibir, após o envio da resposta, o gabarito comentado com explicação de cada alternativa.
- RF04O sistema deve oferecer simulados cronometrados com tempo configurável, reproduzindo as condições do exame oficial.
- RF05O sistema deve registrar as respostas do estudante e calcular o desempenho por área de conhecimento.
- RF06O sistema deve exibir um dashboard com histórico de simulados, percentual de acertos por área e evolução temporal.
- RF07O sistema deve disponibilizar um fórum de discussão por questão, permitindo comentários e respostas entre usuários.
- RF08O administrador deve poder cadastrar, editar e remover questões, incluindo enunciado, alternativas, gabarito e comentário.
- RF09O sistema deve permitir que o estudante marque questões como "favorita" para revisão posterior.
- RF10O sistema deve permitir que a coordenação de curso visualize relatórios de desempenho agregado dos estudantes do seu curso.
- RF11O sistema deve enviar notificações (e-mail ou push) com lembretes de estudo e novas questões disponíveis.
- RF12O sistema deve permitir redefinição de senha via e-mail.

---

5

## Requisitos Não Funcionais

- RNF01**Desempenho:** O tempo de resposta para carregamento de uma questão não deve exceder 2 segundos em conexão 4G.
- RNF02**Disponibilidade:** O sistema deve estar disponível 99,5% do tempo (downtime máximo de \~44 horas/ano).
- RNF03**Responsividade:** A interface deve ser totalmente funcional em dispositivos móveis (telas a partir de 360px) e desktops.
- RNF04**Segurança:** Senhas devem ser armazenadas com hash bcrypt. A comunicação deve ser feita via HTTPS (TLS 1.2+).
- RNF05**Escalabilidade:** O sistema deve suportar ao menos 500 usuários simultâneos sem degradação perceptível.
- RNF06**Usabilidade:** Um novo usuário deve conseguir iniciar seu primeiro simulado em no máximo 3 cliques a partir do login.
- RNF07**Manutenibilidade:** O código deve seguir padrões de documentação e cobertura de testes unitários de ao menos 70%.
- RNF08**Acessibilidade:** A interface deve seguir as diretrizes WCAG 2.1 nível AA.

---

6

## Regras de Negócio

- RN01O gabarito comentado só é exibido após o estudante enviar sua resposta — nunca antes.
- RN02Um simulado iniciado não pode ser pausado; só pode ser encerrado (tempo esgotado ou envio manual). O resultado é computado imediatamente.
- RN03Cada usuário pode realizar o mesmo simulado mais de uma vez, mas cada tentativa é registrada separadamente no histórico.
- RN04Questões marcadas como "inativas" pelo administrador não aparecem nos filtros de estudo nem em novos simulados.
- RN05O relatório de desempenho da coordenação exibe apenas dados agregados — sem identificar individualmente o estudante (conformidade com LGPD).
- RN06Todo conteúdo publicado no fórum passa por moderação antes de ficar visível para outros usuários.
- RN07O cálculo do percentual de acertos considera apenas as questões efetivamente respondidas — questões em branco não penalizam, mas reduzem o denominador.
- RN08Um estudante só pode ter uma conta ativa por e-mail institucional.

---

7

## Backlog Priorizado

Priorização baseada em valor de negócio × complexidade de implementação (método MoSCoW).

| # | História de Usuário | Req. | Prioridade | Sprint |
| --- | --- | --- | --- | --- |
| US01 | Como estudante, quero me cadastrar e fazer login para acessar o sistema com segurança. | RF01, RF12 | Must | 1 |
| US02 | Como estudante, quero filtrar questões por ano, curso e componente para estudar o conteúdo do meu exame. | RF02 | Must | 1 |
| US03 | Como estudante, quero visualizar o gabarito comentado após responder uma questão para entender meu erro. | RF03, RN01 | Must | 1 |
| US04 | Como estudante, quero realizar um simulado cronometrado para treinar nas mesmas condições do ENADE. | RF04, RN02 | Must | 2 |
| US05 | Como estudante, quero ver meu desempenho por área de conhecimento no dashboard para focar no que preciso melhorar. | RF05, RF06 | Must | 2 |
| US06 | Como administrador, quero cadastrar e editar questões para manter o banco de questões atualizado. | RF08 | Must | 2 |
| US07 | Como estudante, quero marcar questões como favoritas para revisar depois. | RF09 | Should | 3 |
| US08 | Como estudante, quero comentar e discutir uma questão no fórum para aprender com outros colegas. | RF07, RN06 | Should | 3 |
| US09 | Como coordenador de curso, quero ver o desempenho agregado do meu curso para identificar áreas críticas. | RF10, RN05 | Should | 3 |
| US10 | Como estudante, quero receber notificações de lembretes de estudo por e-mail para manter minha rotina. | RF11 | Could | 4 |

---

8

## Diagrama de Casos de Uso

Representa as interações entre os atores e as funcionalidades do sistema ENADE+.

UML · Casos de Uso — Mermaid

```
flowchart LR
  subgraph Atores
    EST([👤 Estudante])
    ADM([🔧 Administrador])
    COORD([🏫 Coordenador])
    PROF([📚 Professor])
  end

  subgraph Sistema ENADE+
    UC1[Cadastrar-se / Login]
    UC2[Filtrar Questões]
    UC3[Responder Questão]
    UC4[Ver Gabarito Comentado]
    UC5[Realizar Simulado Cronometrado]
    UC6[Ver Dashboard de Desempenho]
    UC7[Favoritar Questão]
    UC8[Participar do Fórum]
    UC9[Redefinir Senha]

    UC10[Gerenciar Questões]
    UC11[Moderar Fórum]
    UC12[Gerenciar Usuários]

    UC13[Ver Relatório Agregado do Curso]
  end

  EST --> UC1
  EST --> UC2
  EST --> UC3
  UC3 --> UC4
  EST --> UC5
  EST --> UC6
  EST --> UC7
  EST --> UC8
  EST --> UC9

  ADM --> UC1
  ADM --> UC10
  ADM --> UC11
  ADM --> UC12

  COORD --> UC1
  COORD --> UC13

  PROF --> UC1
  PROF --> UC6
  PROF --> UC13
```

**Como usar:** Cole o código acima em [mermaid.live](https://mermaid.live) ou Draw.io para renderizar o diagrama visualmente e exportar como imagem para o relatório final.

### Descrição dos Casos de Uso Principais

| ID | Caso de Uso | Ator Principal | Pré-condição | Resultado |
| --- | --- | --- | --- | --- |
| UC3 | Responder Questão | Estudante | Autenticado, questão selecionada | Resposta registrada; gabarito exibido |
| UC5 | Realizar Simulado | Estudante | Autenticado, simulado configurado | Resultado calculado e salvo no histórico |
| UC6 | Ver Dashboard | Estudante / Professor | Ao menos 1 simulado realizado | Gráficos de desempenho exibidos |
| UC10 | Gerenciar Questões | Administrador | Autenticado como admin | Questão criada, editada ou desativada |

---

9

## Diagrama de Componentes

Descreve os componentes de software do sistema e suas dependências.

UML · Componentes — Mermaid

```
flowchart TB
  subgraph Cliente["Interface (Frontend)"]
    UI_Auth["Módulo de Autenticação\n(Login / Cadastro)"]
    UI_Questoes["Módulo de Questões\n(Filtro + Resposta + Gabarito)"]
    UI_Simulado["Módulo de Simulado\n(Cronômetro + Progresso)"]
    UI_Dashboard["Módulo de Dashboard\n(Gráficos de Desempenho)"]
    UI_Forum["Módulo de Fórum"]
    UI_Admin["Painel Admin\n(CRUD de Questões e Usuários)"]
  end

  subgraph API["API REST (Backend)"]
    SVC_Auth["Serviço de Autenticação\n(JWT + bcrypt)"]
    SVC_Questoes["Serviço de Questões\n(Busca + Filtros)"]
    SVC_Simulado["Serviço de Simulado\n(Sessão + Correção)"]
    SVC_Desempenho["Serviço de Desempenho\n(Cálculo + Relatórios)"]
    SVC_Forum["Serviço de Fórum\n(Posts + Moderação)"]
    SVC_Notif["Serviço de Notificações\n(E-mail / Push)"]
  end

  subgraph Dados["Persistência"]
    DB[("Banco de Dados\n(PostgreSQL)")]
    CACHE[("Cache\n(Redis)")]
  end

  subgraph Externo["Serviços Externos"]
    INEP["Portal INEP\n(Questões oficiais)"]
    EMAIL["Serviço de E-mail\n(SMTP / SendGrid)"]
  end

  UI_Auth --> SVC_Auth
  UI_Questoes --> SVC_Questoes
  UI_Simulado --> SVC_Simulado
  UI_Dashboard --> SVC_Desempenho
  UI_Forum --> SVC_Forum
  UI_Admin --> SVC_Questoes
  UI_Admin --> SVC_Auth

  SVC_Auth --> DB
  SVC_Questoes --> DB
  SVC_Questoes --> CACHE
  SVC_Simulado --> DB
  SVC_Desempenho --> DB
  SVC_Forum --> DB
  SVC_Notif --> EMAIL

  SVC_Questoes -.-> INEP
```

**Como usar:** Cole o código em [mermaid.live](https://mermaid.live) e exporte como SVG ou PNG para inserir no documento entregue.

---

10

## Diagrama de Implantação

Descreve a infraestrutura física/lógica em que o sistema será executado.

UML · Implantação — Mermaid

```
flowchart TB
  subgraph Usuario["Dispositivo do Usuário"]
    BROWSER["Navegador Web\n(Chrome / Safari / Firefox)"]
    MOBILE["Smartphone\n(PWA — iOS / Android)"]
  end

  subgraph CDN["CDN / Edge"]
    EDGE["Servidor de Borda\n(Vercel Edge / Cloudflare)\nAssets estáticos + Cache"]
  end

  subgraph Cloud["Infraestrutura Cloud (AWS / GCP)"]
    subgraph AppTier["Camada de Aplicação"]
      FRONTEND["Frontend Server\n(Next.js)\nPorta 443 HTTPS"]
      BACKEND["API Server\n(Node.js / Express)\nPorta 3001"]
    end

    subgraph DataTier["Camada de Dados"]
      PG[("PostgreSQL\nRDS / Neon\nPorta 5432")]
      REDIS[("Redis\nElastiCache\nPorta 6379")]
    end

    LB["Load Balancer\n(HTTPS)"]
  end

  subgraph ExtSvc["Serviços Externos"]
    SENDGRID["SendGrid\n(E-mail)"]
    INEP_EXT["Portal INEP\n(HTTP API)"]
  end

  BROWSER --> EDGE
  MOBILE --> EDGE
  EDGE --> LB
  LB --> FRONTEND
  FRONTEND --> BACKEND
  BACKEND --> PG
  BACKEND --> REDIS
  BACKEND --> SENDGRID
  BACKEND -.-> INEP_EXT
```

**Como usar:** Cole o código em [mermaid.live](https://mermaid.live) para visualizar e exportar. Alternativamente, importe no Draw.io via File → Import → Mermaid.

### Notas de Infraestrutura

| Componente | Tecnologia sugerida | Justificativa |
| --- | --- | --- |
| Frontend | Next.js + Vercel | SSR para SEO, deploy simplificado, CDN integrada |
| Backend API | Node.js + Express | Ecosistema amplo, integração natural com Next.js |
| Banco de dados | PostgreSQL (Neon) | Relacional, robusto, suporte a queries complexas de desempenho |
| Cache | Redis | Sessões de simulado em tempo real, cache de questões |
| Autenticação | JWT + bcrypt | Stateless, seguro, amplamente adotado |
| E-mail | SendGrid | Plano gratuito suficiente para MVP, API REST simples |

---

P1 — Requisitos e Modelagem de Sistemas · UNIFOR · Sprint 1 (20/10 – 02/11/2026) · Prof. Bezerra
