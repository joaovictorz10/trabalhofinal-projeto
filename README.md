# 🔧 MecânicaPro 🚗

> [!NOTE]
> Sistema completo de gestão para oficinas mecânicas.
> Centraliza ordens de serviço, controle de estoque, agendamentos e pagamentos em uma plataforma web e mobile.

<table>
  <tr>
    <td width="800px">
      <div align="justify">
        O <b>MecânicaPro</b> é um sistema multiplataforma de gestão desenvolvido para oficinas mecânicas de pequeno e médio porte. A plataforma resolve problemas recorrentes do setor, como a perda de informações em ordens de serviço manuais, dificuldade de rastrear o status de veículos em atendimento, controle manual de estoque de peças e a falta de comunicação proativa com clientes. O sistema centraliza o gerenciamento de <i>clientes</i>, <i>veículos</i>, <i>ordens de serviço (OS)</i>, <i>agendamentos</i>, <i>estoque de produtos</i>, <i>pagamentos</i> e <i>relatórios gerenciais</i>, utilizando notificações automáticas por e-mail e SMS para manter o cliente sempre informado. Projeto elaborado como parte da disciplina <b>Projeto de Software</b>.
      </div>
    </td>
  </tr>
</table>

---

## 🚧 Status do Projeto

[![Versão](https://img.shields.io/badge/Versão-v1.0.0-blue?style=for-the-badge)](https://github.com/joaovictorz10/mecanicapro/releases)
![Node.js](https://img.shields.io/badge/Node.js-20.11_LTS-007ec6?style=for-the-badge&logo=nodedotjs&logoColor=white)
![React](https://img.shields.io/badge/React-18.2-007ec6?style=for-the-badge&logo=react&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-007ec6?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-007ec6?style=for-the-badge&logo=docker&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-3.13-007ec6?style=for-the-badge&logo=rabbitmq&logoColor=white)
![Licença](https://img.shields.io/badge/Licença-MIT-green?style=for-the-badge&logo=opensourceinitiative)
![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow?style=for-the-badge)

---

## 📚 Índice

- [🔗 Links Úteis](#-links-úteis)
- [📝 Sobre o Projeto](#-sobre-o-projeto)
- [✨ Funcionalidades Principais](#-funcionalidades-principais)
- [🛠 Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [🏗 Arquitetura](#-arquitetura)
- [🔧 Instalação e Execução](#-instalação-e-execução)
  - [Pré-requisitos](#pré-requisitos)
  - [🔑 Variáveis de Ambiente](#-variáveis-de-ambiente)
  - [📦 Instalação de Dependências](#-instalação-de-dependências)
  - [💾 Inicialização do Banco de Dados](#-inicialização-do-banco-de-dados)
  - [⚡ Como Executar a Aplicação](#-como-executar-a-aplicação)
  - [🐳 Execução com Docker Compose](#-execução-com-docker-compose)
- [🚀 Deploy](#-deploy)
- [📂 Estrutura de Pastas](#-estrutura-de-pastas)
- [🎥 Demonstração](#-demonstração)
- [🧪 Testes](#-testes)
- [🔗 Documentações Utilizadas](#-documentações-utilizadas)
- [👥 Autores](#-autores)
- [🤝 Contribuição](#-contribuição)
- [🙏 Agradecimentos](#-agradecimentos)
- [📄 Licença](#-licença)

---

## 🔗 Links Úteis

- 📖 **Documentação do Projeto:** [Relatório](/relatório/relatoriomecanica.pdf)
- 📋 **Enunciado do Sistema:** [Enunciado](enunciadomecanicapro.pdf)
- 🖼️ **Diagramas UML:** [Pasta diagramas/](diagramas/)
- 💻 **Códigos PlantUML:** [Pasta códigos/](códigos/)
- 🌐 **PlantUML Online:** [plantuml.com/plantuml/uml](https://www.plantuml.com/plantuml/uml/)

---

## 📝 Sobre o Projeto

O **MecânicaPro** nasceu da necessidade de modernizar a gestão operacional de oficinas mecânicas que ainda dependem de processos manuais e planilhas. O problema é real: oficinas que operam sem um sistema integrado perdem em média 3 horas por dia em retrabalho administrativo e apresentam índice de reclamação de clientes significativamente maior pela falta de comunicação sobre o andamento dos serviços.

A plataforma resolve quatro dores centrais:

- **Rastreabilidade:** Cada Ordem de Serviço possui um ciclo de vida rigoroso (Aberta → Em Execução → Aguardando Peça → Concluída → Paga), eliminando a perda de informações.
- **Controle de Estoque:** Baixa automática de peças ao registrar o uso, com alertas de estoque mínimo em tempo real.
- **Comunicação com o cliente:** Notificações automáticas por e-mail e SMS em cada etapa relevante do atendimento.
- **Gestão gerencial:** Relatórios de faturamento, desempenho por mecânico e movimentação de estoque disponíveis para o administrador.

O projeto foi desenvolvido como trabalho acadêmico da disciplina **Projeto de Software**, contemplando modelagem UML completa (Casos de Uso, Classes, Sequência, Comunicação, Estados, Componentes, Implantação e DER) e arquitetura baseada em microsserviços.

---

## ✨ Funcionalidades Principais

### Recepcionista
- 🧑‍💼 **Cadastro de Clientes e Veículos:** Registro completo com CPF, placa, modelo e histórico.
- 📋 **Abertura de Ordem de Serviço:** Vincula cliente, veículo e serviços com cálculo automático do valor estimado.
- 📅 **Agendamentos:** Marcação de atendimentos futuros com lembrete automático 24h antes.
- 💳 **Registro de Pagamentos:** Aceita Dinheiro, Débito, Crédito e Pix, com emissão de comprovante digital.

### Mecânico
- 🔩 **Execução de Serviços:** Visualização das OS atribuídas e registro de peças utilizadas.
- 📦 **Baixa Automática de Estoque:** Ao registrar peças, o estoque é decrementado automaticamente.
- 🔄 **Atualização de Status da OS:** Controle do ciclo de vida (Aberta → Em Execução → Aguardando Peça → Concluída).

### Gerente/Administrador
- 🗂️ **Gestão de Catálogo:** Cadastro e edição de serviços e produtos com controle de preço e estoque mínimo.
- 👥 **Gestão de Usuários:** Cadastro, edição e desativação de recepcionistas e mecânicos.
- 📊 **Relatórios Gerenciais:** Faturamento por período, OS por mecânico, produtos mais utilizados (PDF, CSV, Excel).
- 🚨 **Alertas de Estoque:** Notificação automática quando produto atinge o estoque mínimo.

### Geral
- 🔐 **Autenticação JWT:** Login seguro com controle de permissões por perfil de acesso.
- 📣 **Notificações Automáticas:** E-mail (SMTP) e SMS/WhatsApp (Twilio) em eventos relevantes.

---

## 🛠 Tecnologias Utilizadas

### 💻 Front-end

| Tecnologia | Versão | Finalidade |
|---|---|---|
| [React.js](https://reactjs.org/) | 18.2 | Interface Web (SPA) |
| [React Native](https://reactnative.dev/) | 0.73 | Aplicativo Mobile |
| [TypeScript](https://www.typescriptlang.org/) | 5.3 | Tipagem estática |
| [Tailwind CSS](https://tailwindcss.com/) | 3.4 | Estilização |
| [Axios](https://axios-http.com/) | 1.6 | Requisições HTTP |
| [React Router](https://reactrouter.com/) | 6.21 | Roteamento |

### 🖥️ Back-end

| Tecnologia | Versão | Finalidade |
|---|---|---|
| [Node.js](https://nodejs.org/) | 20.11 LTS | Runtime JavaScript |
| [Express.js](https://expressjs.com/) | 4.18 | Framework HTTP / API Gateway |
| [TypeScript](https://www.typescriptlang.org/) | 5.3 | Tipagem estática |
| [Prisma ORM](https://www.prisma.io/) | 5.8 | ORM / Migrations |
| [JWT](https://jwt.io/) | — | Autenticação stateless |
| [Bcrypt.js](https://github.com/dcodeIO/bcrypt.js) | 2.4 | Hash de senhas |
| [Zod](https://zod.dev/) | 3.22 | Validação de schemas |

### 🗄️ Banco de Dados e Mensageria

| Tecnologia | Versão | Finalidade |
|---|---|---|
| [PostgreSQL](https://www.postgresql.org/) | 16.1 | Banco relacional principal (Primary + Read Replica) |
| [Redis](https://redis.io/) | 7.2 | Cache de sessões e tokens |
| [RabbitMQ](https://www.rabbitmq.com/) | 3.13 | Fila de notificações e eventos assíncronos |

### 📣 Notificações Externas

| Tecnologia | Finalidade |
|---|---|
| [Nodemailer](https://nodemailer.com/) + SMTP Gmail | Envio de e-mails transacionais |
| [Twilio](https://www.twilio.com/) | SMS e WhatsApp |

### ⚙️ Infraestrutura e DevOps

| Tecnologia | Finalidade |
|---|---|
| [Docker](https://www.docker.com/) + Docker Compose | Containerização dos microsserviços |
| [Nginx](https://nginx.org/) | Reverse proxy e HTTPS |
| [Amazon S3](https://aws.amazon.com/s3/) | Armazenamento de documentos e relatórios |
| [GitHub Actions](https://github.com/features/actions) | CI/CD Pipeline |

### 🛠️ Ferramentas de Desenvolvimento e Modelagem

| Ferramenta | Finalidade |
|---|---|
| [PlantUML](https://plantuml.com/) | Geração de todos os diagramas UML |
| [ESLint](https://eslint.org/) + [Prettier](https://prettier.io/) | Linting e formatação de código |
| [Jest](https://jestjs.io/) | Testes unitários |
| [Supertest](https://github.com/ladjs/supertest) | Testes de integração de API |

---

## 🏗 Arquitetura

O sistema adota uma **arquitetura baseada em microsserviços** containerizados com Docker, comunicando-se através de um API Gateway centralizado (Express.js). O Nginx atua como ponto de entrada único, terminando o SSL. A comunicação assíncrona entre serviços utiliza **RabbitMQ**, garantindo desacoplamento no envio de notificações.

| Camada | Componentes |
|---|---|
| **Apresentação** | React.js (Web), React Native (Mobile) |
| **Gateway** | Nginx (Reverse Proxy), Express.js (API Gateway) |
| **Microsserviços** | Usuários, Clientes/Veículos, OS, Estoque, Pagamentos, Notificações, Relatórios |
| **Mensageria** | RabbitMQ |
| **Notificações** | Nodemailer (SMTP), Twilio (SMS/WhatsApp) |
| **Dados** | PostgreSQL 16 (Primary + Read Replica) |
| **Armazenamento** | Amazon S3 |

### 📊 Diagramas UML

| Diagrama | Diagrama |
|:---:|:---:|
| **Casos de Uso** | **Arquitetura C4** |
| <img src="diagramas/casos_de_uso/casodeuso.png" alt="Casos de Uso" width="350px"/> | <img src="diagramas/arquitetura/arquitetura.png" alt="Arquitetura C4" width="350px"/> |
| **Diagrama de Classes** | **Entidade-Relacionamento** |
| <img src="diagramas/classes/classes.png" alt="Classes" width="350px"/> | <img src="diagramas/er/entidaderelacionamento.png" alt="DER" width="350px"/> |
| **Componentes** | **Implantação** |
| <img src="diagramas/componentes_implantacao/componente.png" alt="Componentes" width="350px"/> | <img src="diagramas/componentes_implantacao/implantaçao.png" alt="Implantação" width="350px"/> |
| **Sequência UC-05 (Abrir OS)** | **Sequência UC-08/09 (Executar Serviço)** |
| <img src="diagramas/sequencia/sequenciauc05.png" alt="Sequência UC-05" width="350px"/> | <img src="diagramas/sequencia/sequenciauc0809.png" alt="Sequência UC-08/09" width="350px"/> |
| **Sequência UC-07 (Pagamento)** | **Estados — Ordem de Serviço** |
| <img src="diagramas/sequencia/sequenciauc07.png" alt="Sequência UC-07" width="350px"/> | <img src="diagramas/estados/estadoordemdeservico.png" alt="Estados OS" width="350px"/> |
| **Estados — Agendamento** | **Estados — Produto (Estoque)** |
| <img src="diagramas/estados/estadoagendamento.png" alt="Estados Agendamento" width="350px"/> | <img src="diagramas/estados/estadoproduto.png" alt="Estados Produto" width="350px"/> |
| **Comunicação UC-05** | **Comunicação UC-08/09** |
| <img src="diagramas/comunicacao/comunicacao05.png" alt="Comunicação UC-05" width="350px"/> | <img src="diagramas/comunicacao/comunicacao0809.png" alt="Comunicação UC-08/09" width="350px"/> |

---

## 🔧 Instalação e Execução

### Pré-requisitos

- **Node.js:** v20.x LTS ou superior
- **Docker** e Docker Compose
- **Git**
- **npm** ou **yarn**

---

### 🔑 Variáveis de Ambiente

Crie um arquivo **`.env`** na raiz do projeto baseado no `.env.example`:

```env
# Banco de Dados
DATABASE_URL=postgresql://mecanicapro:senha@localhost:5432/mecanicapro_db

# JWT
JWT_SECRET=sua_chave_secreta_aqui
JWT_EXPIRES_IN=8h

# RabbitMQ
RABBITMQ_URL=amqp://localhost:5672

# E-mail (SMTP Gmail)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=mecanicapro@gmail.com
SMTP_PASS=sua_senha_de_app

# Twilio (SMS/WhatsApp)
TWILIO_ACCOUNT_SID=ACxxxxxxxxxxxxxxxx
TWILIO_AUTH_TOKEN=xxxxxxxxxxxxxxxx
TWILIO_PHONE=+5511999999999

# Amazon S3
AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG
AWS_REGION=us-east-1
AWS_BUCKET=mecanicapro-files
```

---

### 📦 Instalação de Dependências

1. **Clone o repositório:**

```bash
git clone https://github.com/joaovictorz10/mecanicapro.git
cd mecanicapro
```

2. **Instale as dependências do backend:**

```bash
cd backend
npm install
cd ..
```

3. **Instale as dependências do frontend:**

```bash
cd frontend
npm install
cd ..
```

---

### 💾 Inicialização do Banco de Dados

Suba o PostgreSQL via Docker:

```bash
docker run --name mecanicapro_db \
  -e POSTGRES_USER=mecanicapro \
  -e POSTGRES_PASSWORD=senha \
  -e POSTGRES_DB=mecanicapro_db \
  -p 5432:5432 -d postgres:16
```

Execute as migrations com o Prisma:

```bash
cd backend
npx prisma migrate dev
```

---

### ⚡ Como Executar a Aplicação

Execute em **dois terminais separados**:

#### Terminal 1 — Back-end

```bash
cd backend
npm run dev
```

🚀 API disponível em **http://localhost:3000**

#### Terminal 2 — Front-end

```bash
cd frontend
npm run dev
```

🎨 Interface disponível em **http://localhost:5173**

---

### 🐳 Execução com Docker Compose

Para subir toda a stack (backend, frontend, PostgreSQL, RabbitMQ) de uma vez:

```bash
# Sobe todos os serviços em background
docker-compose up --build -d

# Verifica os containers rodando
docker ps

# Para e remove os containers
docker-compose down
```

---

## 🚀 Deploy

1. **Build do front-end:**

```bash
cd frontend
npm run build
```

2. **Build do back-end:**

```bash
cd backend
npm run build
```

3. **Configure as variáveis de ambiente** no seu provedor (VPS, Railway, Render, etc.) conforme o `.env.example`.

4. **Execução em produção:**

```bash
# Back-end
node backend/dist/server.js

# Front-end (arquivos estáticos servidos pelo Nginx)
# Configurar o Nginx para apontar para frontend/dist
```

---

## 📂 Estrutura de Pastas

```
mecanicapro/
│
├── códigos/                              # Diagramas PlantUML organizados por tipo
│   ├── arquitetura/
│   │   └── Diagrama_C4_Arquitetura.puml
│   ├── casos_de_uso/
│   │   └── Caso de uso.puml
│   ├── classes/
│   │   └── Diagrama_Classes.puml
│   ├── componentes_implantacao/
│   │   └── Diagrama_Componentes_Implantacao.puml
│   ├── comunicacao/
│   │   └── Diagrama_Comunicacao.puml
│   ├── er/
│   │   └── Diagrama_ER.puml
│   ├── estados/
│   │   └── Diagrama_Estados.puml
│   └── sequencia/
│       └── Diagrama_Sequencia.puml
│
├── diagramas/                            # Imagens renderizadas dos diagramas
│   ├── arquitetura/
│   ├── casos_de_uso/
│   ├── classes/
│   ├── componentes_implantacao/
│   ├── comunicacao/
│   ├── er/
│   ├── estados/
│   └── sequencia/
│
├── backend/                              # API Node.js / Express (microsserviços)
│   ├── src/
│   │   ├── controllers/                  # Endpoints REST
│   │   ├── services/                     # Regras de negócio
│   │   ├── repositories/                 # Acesso ao banco (Prisma)
│   │   ├── middlewares/                  # Auth JWT, validação, rate limit
│   │   ├── routes/                       # Definição de rotas
│   │   └── utils/                        # Funções auxiliares
│   ├── prisma/
│   │   └── schema.prisma                 # Schema do banco de dados
│   ├── .env.example
│   └── package.json
│
├── frontend/                             # React.js (Web)
│   ├── src/
│   │   ├── components/                   # Componentes reutilizáveis
│   │   ├── pages/                        # Páginas da aplicação
│   │   ├── services/                     # Chamadas à API
│   │   ├── hooks/                        # Hooks personalizados
│   │   └── utils/                        # Funções utilitárias
│   ├── .env.example
│   └── package.json
│
├── docker-compose.yml                    # Orquestração dos containers
├── Documentacao_MecanicaPro.pdf          # Relatório completo de projeto
├── Documentacao_MecanicaPro.md           # Fonte do relatório (Markdown)
├── Enunciado_MecanicaPro.pdf             # Enunciado do sistema
├── README.md                             # Este arquivo
└── .gitignore
```

---

## 🎥 Demonstração

### 🌐 Aplicação Web

| Tela | Captura de Tela |
|:---:|:---:|
| **Abertura de OS** | **Gestão de Estoque** |
| *(inserir print)* | *(inserir print)* |
| **Dashboard Gerencial** | **Registro de Pagamento** |
| *(inserir print)* | *(inserir print)* |

### 📱 Aplicativo Mobile (Mecânico)

| Tela | Tela | Tela |
|:---:|:---:|:---:|
| **OS Atribuídas** | **Execução de Serviço** | **Consulta de Estoque** |
| *(inserir print)* | *(inserir print)* | *(inserir print)* |

---

## 🧪 Testes

### Testes Unitários

```bash
cd backend
npm run test
```

### Testes de Integração (API)

```bash
cd backend
npm run test:integration
```

### Cobertura de Testes

```bash
npm run test:coverage
```

---

## 🔗 Documentações Utilizadas

- 📖 [PlantUML — Documentação Oficial](https://plantuml.com/)
- 📖 [Prisma ORM — Documentação](https://www.prisma.io/docs)
- 📖 [Express.js — Documentação](https://expressjs.com/)
- 📖 [React — Documentação Oficial](https://react.dev/)
- 📖 [PostgreSQL 16 — Documentação](https://www.postgresql.org/docs/16/)
- 📖 [RabbitMQ — Documentação](https://www.rabbitmq.com/documentation.html)
- 📖 [Docker — Documentação](https://docs.docker.com/)
- 📖 [Twilio API — Documentação](https://www.twilio.com/docs)
- 📖 [Nodemailer — Documentação](https://nodemailer.com/about/)
- 📖 [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)

---

## 👥 Autores

| 👤 Autor | 🖼️ Perfil | :octocat: GitHub | 💼 LinkedIn | 📤 Contato |
|---------|----------|-----------------|-------------|-----------|
| **João Victor Russo Marquito** | <div align="center"><img src="https://github.com/joaovictorz10.png" width="55px" height="55px"></div> | <div align="center"><a href="https://github.com/joaovictorz10"><img src="https://joaopauloaramuni.github.io/image/github6.png" width="35px" height="35px"></a></div> | <div align="center"><a href="https://www.linkedin.com/in/joaovictor-russo/"><img src="https://joaopauloaramuni.github.io/image/linkedin2.png" width="35px" height="35px"></a></div> | <div align="center"><a href="mailto:devjoaovictor9@gmail.com"><img src="https://joaopauloaramuni.github.io/image/gmail3.png" width="35px" height="35px"></a></div> |

---

## 🤝 Contribuição

1. Faça um `fork` do projeto.
2. Crie uma branch para sua feature:
   ```bash
   git checkout -b feature/minha-feature
   ```
3. Commit suas mudanças seguindo [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/):
   ```bash
   git commit -m 'feat: adiciona nova funcionalidade X'
   ```
4. Faça o push para a branch:
   ```bash
   git push origin feature/minha-feature
   ```
5. Abra um **Pull Request**.

> [!IMPORTANT]
> Certifique-se de que os testes passam antes de abrir o PR: `npm run test`

---

## 🙏 Agradecimentos

- [**Prof. Dr. João Paulo Aramuni**](https://github.com/joaopauloaramuni) — Pelos ensinamentos em Arquitetura de Software, Projeto de Software e modelagem UML.
- [**PUC Minas — Engenharia de Software**](https://www.instagram.com/engsoftwarepucminas/) — Pelo apoio institucional e estrutura acadêmica.
- [**PlantUML Community**](https://plantuml.com/) — Pela ferramenta de diagramação utilizada em todo o projeto.

---

## 📄 Licença

Este projeto é distribuído sob a **Licença MIT**.  
Desenvolvido como trabalho acadêmico para a disciplina **Projeto de Software — PUC Minas**.
