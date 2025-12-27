# 🗓️ Clienda - Plataforma SaaS de Agendamentos Multi-tenant

O **Clienda** é uma solução robusta de agendamento e gestão para consultórios e clínicas, concebida sob o modelo **SaaS (Software as a Service)**. O foco principal do projeto é a escalabilidade e o isolamento total de dados entre clientes através de subdomínios dinâmicos.

---

### 🚀 Destaques de Engenharia

Este projeto foi desenvolvido para resolver problemas reais de arquitetura de software, indo além de um simples CRUD:

* **Arquitetura Multi-tenant:** Implementação de Middlewares no Next.js para gestão de subdomínios dinâmicos (ex: `clinica.clienda.com`), garantindo que cada cliente tenha o seu ambiente isolado.
* **Fluxo de Pagamentos Completo:** Integração nativa com a **API do Stripe**, tratando desde o checkout, gestão de planos e cupões, até o processamento de Webhooks para sincronização de subscrições.
* **Comunicação em Tempo Real:** Sistema de notificações instantâneas utilizando **Pusher**, eliminando a necessidade de refresh para atualizações críticas no dashboard.
* **Segurança e RBAC:** Autenticação robusta com controlo de acesso baseado em funções (Admin, Staff e Cliente).

---

### 🛠️ Stack Tecnológica

* **Framework:** [Next.js 15](https://nextjs.org/) (App Router)
* **Linguagem:** [TypeScript](https://www.typescriptlang.org/)
* **Estilização:** [Tailwind CSS](https://tailwindcss.com/)
* **Base de Dados & ORM:** [PostgreSQL](https://www.postgresql.org/) com [Prisma ORM](https://www.prisma.io/)
* **Pagamentos:** [Stripe SDK](https://stripe.com/)
* **Real-time:** [Pusher](https://pusher.com/)
* **Componentes UI:** Radix UI / Lucide Icons

---

### 📋 Funcionalidades Principais

* **Painel Administrativo:** Gestão centralizada de empresas, utilizadores, planos e cupões de desconto.
* **Dashboard do Lojista:** Visão analítica de agendamentos, faturação e gestão de equipas.
* **Agenda Inteligente:** Marcação de horários com validação automática de disponibilidade em tempo real.
* **CRM Interno:** Gestão de clientes com histórico de marcações e observações personalizadas.
* **Notificações Dinâmicas:** Alertas em tempo real sobre novos agendamentos e alterações de status.

---

### 🧠 Decisões de Arquitetura

**Porquê Subdomínios Dinâmicos?**
Para proporcionar uma experiência profissional e personalizada a cada cliente (tenant). A lógica foi centralizada no `middleware.ts`, que interseta as requisições e mapeia o subdomínio para o ID correto da empresa na base de dados.

**Modelagem de Dados com Prisma:**
A estrutura foi desenhada para suportar relações complexas. Um destaque é a lógica de permissões vinculada ao plano de subscrição: certas funcionalidades são bloqueadas ou libertadas automaticamente dependendo do status da assinatura no Stripe.

---

### 🔧 Como Executar

1. **Clonar o Repositório:**
   ```bash
   git clone [https://github.com/teu-utilizador/clienda.git](https://github.com/teu-utilizador/clienda.git)

Instalar Dependências:

  ```bash

npm install
Configuração .env: Configurar as variáveis do Stripe, Pusher e o DATABASE_URL.

Base de Dados:

npx prisma migrate dev
Iniciar:

npm run dev

---
