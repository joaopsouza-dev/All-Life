# All-# All Life

Um projeto pessoal de produtividade e desenvolvimento — uma aplicação web que centraliza agenda, hábitos, estudos e motivação em um único lugar, construída do zero como laboratório de aprendizado full stack.

## Sobre

**All Life** nasceu de uma ideia simples: por que usar 5 aplicativos diferentes quando você poderia usar um? O projeto reúne funcionalidades que normalmente estão espalhadas (Google Agenda, Trello, Strava, Skoob, Notion, Hevy, Focus To-Do, etc.) em um sistema coeso, minimalista e unificado.

A diferença não está em ser o melhor calendário, o melhor app de fitness ou o melhor de notas — está em **integrar tudo isso de forma simples**. Ter um lugar único onde você:

- Anota seus compromissos do dia
- Marca seus hábitos concluídos
- Registra uma sessão de estudo
- Vê uma frase motivacional
- Acompanha sua evolução pessoal

Tudo em uma única aplicação, com dados armazenados permanentemente para análise futura.

Mas acima de tudo, **All Life é um laboratório de aprendizado**. É meu primeiro projeto full stack completo, e o objetivo não é apenas construir uma aplicação funcional, mas realmente entender:

- Como backend, frontend e banco de dados trabalham juntos
- Padrões de arquitetura e design de software
- Testes unitários e de integração
- Autenticação e autorização
- API REST e contratos de dados
- Boas práticas de versionamento e git

## Motivação

O projeto pretende resolver alguns problemas reais que enfrentei e que muitas pessoas enfrentam:

**Fragmentação de ferramentas**: Quando você quer ser produtivo, você acaba usando: Google Agenda (compromissos), Notion ou Trello (anotações), Strava ou app de academia (treinos), Skoob (leitura), timer separado (Pomodoro), app financeiro (gastos). Cada uma em um lugar diferente, sem integração. All Life traz tudo para um lugar.

**Falta de visibilidade da rotina**: Você não sabe ao certo quantas horas estudou esta semana, quantos treinos fez este mês, quantos livros já leu este ano, ou o quão consistente realmente foi com seus hábitos. Os dados ficam espalhados ou são perdidos.

**Dificuldade em manter hábitos**: Pesquisa mostra que ver o progresso visual (streaks, gráficos, recaps) aumenta a motivação. All Life oferece isso de forma clara e lúdica.

**Falta de feedback sobre evolução**: Não é suficiente apenas registrar dados. Você quer saber: *Como estou evoluindo? Estou melhorando? Qual é meu maior progresso?* All Life vai além do registro — propõe análise e feedback.

## Stack Tecnológica

### Core (MVP)

- **Backend**: Java 17+ com Spring Boot 3.x
  - Spring Data JPA para persistência
  - Spring Security para autenticação
  - Spring Web para REST API
  
- **Frontend**: React 18+ (a ser aprendido durante o projeto)
  - React Router para navegação
  - Axios para requisições HTTP
  - CSS/Tailwind para styling (a definir)
  
- **Banco de dados**: PostgreSQL 13+
  - Migrations com Flyway
  - ORM via JPA/Hibernate
  
- **Versionamento**: Git + GitHub
  - Feature branches para cada módulo
  - Commits semânticos
  
- **Testes**: 
  - JUnit 5 e Mockito para testes unitários
  - Testcontainers para testes de integração
  - Cobertura mínima de 70%

### Desenvolvimento

- **Build**: Maven
- **IDE**: IntelliJ IDEA ou VS Code
- **API Testing**: Postman ou Insomnia
- **Prototipagem**: Figma

### Futuro (V2/V3)

- **Containerização**: Docker + Docker Compose (fase posterior)
- **CI/CD**: GitHub Actions
- **Autenticação Social**: OAuth 2.0 (Google, Apple, Instagram)
- **IA/LLM**: Integração com APIs de LLM para feedback personalizado
- **Mobile**: iOS com Swift (expansão de médio prazo)
- **Analytics**: Integração com ferramentas de análise de dados

## Estrutura do Projeto

O desenvolvimento está organizado em três versões principais, cada uma representando um incremento funcional significativo:

### V1 — MVP (Versão 1)

O núcleo mínimo viável da aplicação. Foco em ter um sistema pequeno, mas **completo de ponta a ponta** (banco → backend → API → frontend). O objetivo é conseguir uma versão funcional e testada antes de adicionar complexidade.

**Módulos**:
- **Autenticação**: Login e signup com email + senha. Segurança básica com hash de senha e JWT para tokens.
- **Home/Dashboard**: Agregador visual de informações. Mostra saudação personalizada, frase motivacional do dia, próximos compromissos, resumo do que foi realizado, e hábitos do dia com checkboxes.
- **Agenda/Calendário**: Registro e visualização de compromissos. Vista por dia (padrão), possibilidade de trocar para semana. CRUD completo de compromissos com data, hora, duração e categoria.
- **Hábitos**: To-do list de hábitos com gamificação. Cálculo automático de streak, histórico de cumprimento, frequência (diário, semanal, mensal, anual).
- **Estudos**: Disciplinas com registro de tempo estudado. Cada disciplina agrupa conteúdos (pendentes e concluídos). Integração com Pomodoro simples.
- **Pomodoro**: Timer básico com opções de duração pré-definidas (25min, 5min, 15min). Quando termina, registra tempo estudado na disciplina.
- **Motivação**: Frase motivacional estática que muda uma vez por dia. Exibida no topo da Home.

**Entidades principais**: User, Compromisso, Habito, HistoricoHabito, Disciplina, Conteudo, SessaoPomodoro, Frase.

### V2 — Expansão (Versão 2)

Adiciona os módulos que dependem de métricas mais específicas e histórico de dados. Essas funcionalidades complementam a base da V1 e começam a oferecer valor real em termos de análise.

**Módulos adicionais**:
- **Treinamentos**: Registro multimodal de exercícios.
  - Corrida/Caminhada: distância, tempo decorrido, tempo total (sem pausa), pace por km, pace médio, calorias.
  - Musculação: exercício, séries, repetições, carga, tempo de descanso.
  - Natação: tempo decorrido, tempo total, pace por 100m, pace médio, calorias.
  - Bicicleta: distância, tempo decorrido, tempo total, pace, pace médio, calorias.
  - Histórico completo com cálculos de progressão de carga e frequência.

- **Leitura**: Biblioteca pessoal de livros.
  - Statuses: para ler, lendo, lido.
  - Rastreamento de progresso (página atual vs. total).
  - Requisitos para finalizar: nota, resenha (mínimo 20 caracteres), data de término.
  - Integração com Pomodoro para contabilizar tempo de leitura.

- **Histórico e Estatísticas Básicas**: 
  - Agregação de dados por semana, mês e ano.
  - Comparações simples entre períodos.
  - Gráficos de evolução (exemplos: horas estudadas por semana, frequência de treino, número de hábitos cumpridos).
  - Rastreamento de dados permanentes sem limite de tempo.

**Novas entidades**: Treino, RegistroTreino, Livro, RegistroLeitura, Estatistica.

### V3 — Futuro (Versão 3 e além)

Evoluções de médio/longo prazo que dependem de mais maturidade do sistema ou de decisões arquiteturais ainda em aberto.

- **Financeiro completo**: Receitas, despesas categorizadas, parcelamentos, metas de limite de gasto, orçamento mensal com análise e feedback.
- **Feedback com IA/LLM**: Análises personalizadas geradas a partir de dados acumulados (ex.: "Você estudou 18% a mais esta semana").
- **OAuth social**: Login via Google, Apple e Instagram.
- **Docker e CI/CD**: Containerização da aplicação e deploy automatizado.
- **Recaps temáticos**: Resumos mensais e anuais estilo Spotify Wrapped.
- **Multiusuário e comunidade**: Compartilhamento de hábitos, desafios entre usuários, leaderboards.
- **Widgets de sistema**: Integração com tela inicial e tela de bloqueio (Android/iOS).
- **Aplicativo mobile**: Versão nativa iOS com Swift.

## Como Começar

### Pré-requisitos

Antes de clonar o repositório, certifique-se de ter instalado:

- **Java Development Kit (JDK) 17 ou superior**
  - Verifique com: `java -version`
  - Download: [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/)

- **PostgreSQL 13 ou superior**
  - Verifique com: `psql --version`
  - Download: [https://www.postgresql.org/download/](https://www.postgresql.org/download/)
  - Certifique-se de que o serviço está rodando

- **Node.js 16+ e npm** (será necessário quando o frontend começar)
  - Verifique com: `node --version` e `npm --version`
  - Download: [https://nodejs.org/](https://nodejs.org/)

- **Git**
  - Verifique com: `git --version`
  - Download: [https://git-scm.com/](https://git-scm.com/)

- **IDE ou editor de código** (recomendado)
  - IntelliJ IDEA Community (backend Java)
  - VS Code (backend, frontend, geral)
  - Qualquer editor que você prefira

### Instalação e Setup

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/all-life.git
cd all-life

# Neste momento, a estrutura inicial ainda não possui backend/frontend
# Atualizações sobre setup serão adicionadas conforme cada componente for adicionado
```

**Nota**: O projeto está ainda na fase de especificação e design. Instruções de setup de desenvolvimento serão adicionadas assim que o backend começar a ser implementado.

### Estrutura de Branches

Conforme o projeto avance, usaremos a seguinte estratégia de branching:

```
main (sempre estável)
├── develop (integração de features)
│   ├── feature/auth (autenticação)
│   ├── feature/agenda (módulo de agenda)
│   ├── feature/habits (módulo de hábitos)
│   └── ...
└── hotfix/* (correções críticas)
```

## Roadmap

Atualmente, o projeto está na fase de **especificação de requisitos e prototipação**. A sequência planejada é:

### Fase 1: Design e Arquitetura (Atual)
- [x] Ideação e especificação de requisitos (V1, V2, V3)
- [x] Prototipação visual no Figma
- [ ] Revisão e aprovação dos Requisitos Funcionais
- [ ] Modelagem de domínio (entidades e atributos)
- [ ] Diagrama ER (Entity-Relationship)
- [ ] Design detalhado da API REST (endpoints, contratos)

### Fase 2: Backend (Próxima)
- [ ] Setup inicial do projeto Spring Boot
- [ ] Configuração do banco de dados PostgreSQL
- [ ] Implementação de entidades JPA
- [ ] Implementação de repositórios
- [ ] Implementação de serviços e regras de negócio
- [ ] Autenticação e autorização (JWT)
- [ ] Controllers REST (endpoints da V1)
- [ ] Testes unitários (cobertura mínima 70%)
- [ ] Testes de integração

### Fase 3: Frontend (Paralela ou após Backend)
- [ ] Setup inicial do projeto React
- [ ] Setup de roteamento (React Router)
- [ ] Componentes base (botões, inputs, cards, etc.)
- [ ] Páginas de autenticação (login/signup)
- [ ] Home/Dashboard
- [ ] Módulo de Agenda
- [ ] Módulo de Hábitos
- [ ] Módulo de Estudos com Pomodoro
- [ ] Integração com API do backend
- [ ] Testes (unitários e E2E)

### Fase 4: V2 e Polimento
- [ ] Módulos de Treinamentos
- [ ] Módulo de Leitura
- [ ] Histórico e estatísticas básicas
- [ ] Refinamento da UX/UI baseado em feedback
- [ ] Otimizações de performance

### Fase 5: V3 e Expansões
- [ ] Financeiro
- [ ] IA/LLM para feedback
- [ ] Docker e CI/CD
- [ ] Mobile iOS com Swift

A data estimada para cada fase será definida conforme o desenvolvimento avançar.

## Documentação

A documentação está organizada em arquivo e será expandida conforme o projeto evolui:

### Documentação Atual

- **[Especificação de Requisitos v0.1](./docs/All_Life_Especificacao_de_Requisitos_v0.1.docx)** 
  - Detalhamento completo de todos os Requisitos Funcionais (RF)
  - Requisitos Não Funcionais (RNF)
  - Regras de Negócio (RN)
  - Organizados por módulo e por versão (V1, V2, V3)
  - Próxima etapa recomendada após leitura

- **[Wireframes e Prototipação](./docs/FIGMA_PROMPT.md)** 
  - Guia completo para prototipação visual no Figma
  - Descrição de todas as telas do MVP
  - Componentes de design, paleta de cores, tipografia
  - Fluxo de interações do usuário

### Documentação Futura (será adicionada conforme necessário)

- **Modelo de Domínio**: Definição de entidades, atributos e relacionamentos
- **Diagrama ER**: Relacionamentos entre tabelas do banco
- **Schema PostgreSQL**: Scripts de criação de banco e migrations
- **Arquitetura de Software**: Padrões de design, camadas, organização de pacotes
- **API REST**: Documentação de endpoints, contratos JSON, exemplos de requisição/resposta
- **Decisões Arquiteturais**: ADRs (Architecture Decision Records) explicando por quê certas escolhas foram feitas
- **Guia de Contribuição**: Padrões de código, processo de PR, checklist antes de merge
- **FAQ e Troubleshooting**: Soluções para problemas comuns durante setup e desenvolvimento

## Princípios de Desenvolvimento

Este projeto segue alguns princípios fundamentais que guiam cada decisão:

### Aprendizado antes de velocidade
O objetivo é entender como tudo funciona, não apenas ter código rodando o mais rápido possível. Significa que às vezes escolheremos a implementação mais educativa em vez da mais rápida. Cada linha de código deve ensinar algo.

### Domínio primeiro, código depois
Antes de escrever qualquer código, entender bem o domínio do problema, requisitos e arquitetura. Nenhuma classe é criada sem entender por quê ela existe. Nenhum banco sem desenhar o diagrama ER primeiro.

### Nenhuma complexidade desnecessária
Não adicionar tecnologia, padrão ou funcionalidade só para parecer mais avançado. Cada decisão deve ter uma razão prática. Começamos simples e adicionamos complexidade apenas quando ela resolver um problema real.

### Desenvolvimento incremental
MVP enxuto primeiro, evoluções depois. Nunca tentar implementar tudo de uma vez. A V1 é pequena propositalmente — é um sistema completo (banco → backend → frontend) que já funciona, antes de adicionar mais módulos.

### Módulos funcionalmente independentes
Cada módulo (Agenda, Hábitos, Estudos, etc.) pode funcionar por si mesmo. Porém, podem compartilhar dados indiretamente através da Home — sem acoplamento direto entre eles.

```
                ALL LIFE
                   │
        ┌──────────┼──────────┐
        ↓          ↓          ↓
     Agenda    Hábitos    Estudos
        ↓          ↓          ↓
        └──────────┼──────────┘
                   ↓
                  Home
              (agregador)
```

### Dados permanentes
Nenhuma exclusão automática ou baseada em limite de tempo. Tudo é armazenado permanentemente para permitir análises de longo prazo. Um hábito "quebrado" ainda tem seu histórico preservado.

### Testes como documentação
Testes não são apenas validação — são documentação viva de como o sistema funciona. Alguém lendo seus testes deve entender o que cada função faz.

## Contribuindo

Este é um projeto pessoal de aprendizado, então não há contribuições externas no momento. O objetivo é construir e aprender de forma independente.

**Porém**, se você tiver:
- **Sugestões de funcionalidades**: Abra uma issue com a tag `suggestion`
- **Feedback sobre design**: Discussion ou issue
- **Questões ou ideias**: Fique à vontade para discutir via issues

Acompanhamentos do desenvolvimento acontecem através de commits e pull requests neste repositório. Cada feature tem sua própria branch e PR associado para rastreamento claro.

## Estrutura do Repositório

```
all-life/
│
├── docs/                                    # Toda documentação do projeto
│   ├── All_Life_Especificacao_de_Requisitos_v0.1.docx
│   ├── FIGMA_PROMPT.md                      # Guia para prototipação no Figma
│   ├── DOMAIN_MODEL.md                      # Modelo de domínio (futuro)
│   ├── ER_DIAGRAM.md                        # Diagrama de relacionamentos (futuro)
│   ├── API_DOCUMENTATION.md                 # Especificação de endpoints REST (futuro)
│   ├── ARCHITECTURE.md                      # Decisões arquiteturais (futuro)
│   └── CONTRIBUTING.md                      # Guia para contribuidores (futuro)
│
├── backend/                                 # Projeto Spring Boot (iniciando em breve)
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/br/com/alllife/
│   │   │   │   ├── domain/                  # Entidades do domínio
│   │   │   │   ├── repository/              # Acesso a dados (JPA)
│   │   │   │   ├── service/                 # Lógica de negócio
│   │   │   │   ├── controller/              # Endpoints REST
│   │   │   │   ├── dto/                     # Objetos de requisição/resposta
│   │   │   │   ├── security/                # Configuração de segurança
│   │   │   │   ├── exception/               # Exceções customizadas
│   │   │   │   └── AllLifeApplication.java  # Classe principal
│   │   │   └── resources/
│   │   │       ├── application.yml          # Configurações
│   │   │       └── db/migration/            # Migrations (Flyway)
│   │   └── test/
│   │       └── java/br/com/alllife/        # Testes unitários e de integração
│   │
│   ├── pom.xml                              # Dependências Maven
│   ├── .gitignore                           # Ignora arquivos compilados
│   └── README.md                            # Setup específico do backend
│
├── frontend/                                # Projeto React (iniciando após backend)
│   ├── src/
│   │   ├── components/                      # Componentes React
│   │   ├── pages/                           # Páginas principais
│   │   ├── services/                        # Chamadas à API
│   │   ├── hooks/                           # Custom hooks
│   │   ├── utils/                           # Funções utilitárias
│   │   ├── styles/                          # CSS/Tailwind
│   │   └── App.jsx                          # Componente raiz
│   │
│   ├── public/
│   ├── package.json                         # Dependências npm
│   ├── .gitignore
│   └── README.md                            # Setup específico do frontend
│
├── database/                                # Scripts e configurações de banco
│   ├── schema.sql                           # Schema inicial (futuro)
│   └── migrations/                          # Scripts Flyway (futuro)
│
├── .github/
│   └── workflows/                           # CI/CD com GitHub Actions (futuro)
│       └── tests.yml
│
├── README.md                                # Este arquivo
├── .gitignore                               # Arquivos ignorados globalmente
└── LICENSE                                  # Licença do projeto
```

**Notas sobre a estrutura**:
- Backend usa estrutura em camadas: controller → service → repository
- Frontend segue padrão React moderno: components, pages, hooks, services
- Documentação é versionada junto com o código
- Cada pasta pode ter seu próprio README específico
- A estrutura evoluirá conforme o projeto crescer

## Aprendizados e Notas

Conforme o desenvolvimento avança, este espaço documentará:

- Decisões arquiteturais importantes e por que foram tomadas
- Problemas encontrados e como foram resolvidos
- Padrões de design aplicados em cada módulo
- Reflexões sobre o processo de aprendizado
- Artigos e recursos que ajudaram no desenvolvimento

Essas notas serão mantidas em uma wiki ou em arquivo separado para que outros possam aprender com o processo.

## Roadmap Pessoal

Além de construir a aplicação, este projeto também é uma oportunidade para:

- Dominar Spring Boot e arquitetura backend em Java
- Aprender React e desenvolvimento frontend moderno
- Entender design de banco de dados relacional
- Praticar testes automatizados (unitários, integração, E2E)
- Aprender boas práticas de versionamento e CI/CD
- Entender autenticação, autorização e segurança de aplicações web
- Melhorar habilidades de design de UX/UI
- Ganhar experiência real com um projeto de escopo real

## Status Atual

- **Fase**: Especificação e Design
- **Último Update**: Setembro de 2026
- **Próximo Marco**: Iniciar implementação do backend (Spring Boot)

## Contato

**Nome**: João Pedro Souza Pereira

**Formação**: Aluno do 3º semestre do curso de Análise e Desenvolvimento de Sistemas na UCB (Universidade Católica de Brasília)

**GitHub**: [@joaopsouza-dev](https://github.com/joaopsouza-dev)

**Email**: contato.joaopsouzap@gmail.com

Feedback, sugestões e questões sobre o projeto são bem-vindos!

---

## Licença

Este projeto é fornecido como está para fins educacionais e pessoais. Sinta-se livre para usar como referência, aprender com o código e implementar ideias similares em seus próprios projetos.

---

**Última atualização**: Setembro de 2026
