# Trackly — CRM de Funil de Vendas

Trackly é uma aplicação web de CRM focada em funil de vendas no formato Kanban. O objetivo é permitir que um usuário administrador gerencie leads ao longo de estágios de vendas, acompanhe clientes e controle o status de cada oportunidade de negócio.

---

## Objetivo

Oferecer uma interface simples e direta para organizar o processo comercial, visualizando leads em colunas que representam cada etapa do funil — desde o primeiro contato até o fechamento ou perda do negócio.

---

## Funcionalidades do MVP

- Autenticação com JWT (usuário único criado via seed)
- Visualização do funil de vendas em formato Kanban
- Mudança de estágio do lead via dropdown
- Cadastro e listagem de clientes
- Controle de status do lead: ativo, ganho ou perdido
- Registro de valor, data de fechamento e motivo de perda

---

## Tecnologias

### Back-end
- Node.js + Express
- Prisma ORM
- PostgreSQL via Supabase
- JWT para autenticação
- bcryptjs para hash de senha

### Front-end
- React + TypeScript
- Tailwind CSS
- Vite
- Axios

---

## Entidades

| Entidade | Descrição |
|----------|-----------|
| `User` | Usuário administrador do sistema |
| `Client` | Cliente vinculado a um ou mais leads |
| `Stage` | Estágio do funil (ex: Prospecção, Proposta, Fechamento) |
| `Lead` | Oportunidade de negócio vinculada a um cliente e um estágio |

---

## Estrutura do Back-end

```
trackly-api/
├── prisma/
│   ├── schema.prisma
│   └── seed.js
├── src/
│   ├── routes/
│   ├── controllers/
│   ├── services/
│   └── middlewares/
├── .env
└── server.js
```

---

## Como rodar o projeto

### Pré-requisitos
- Node.js 18+
- Conta no Supabase com projeto criado

### Instalação

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/trackly-api.git
cd trackly-api

# Instale as dependências
npm install

# Configure o .env
cp .env.example .env
# Preencha DATABASE_URL e JWT_SECRET

# Rode as migrations
npx prisma migrate dev

# Crie o usuário admin via seed
npx prisma db seed

# Inicie o servidor
npm run dev
```

---

## Fora do escopo do MVP (Fase 2)

- Dashboard com métricas e gráficos
- Drag-and-drop no Kanban
- Múltiplos usuários com permissões

---

## Autor

Desenvolvido por Adriel Pereira como projeto de portfólio.
