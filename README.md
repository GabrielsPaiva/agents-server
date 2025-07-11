# NLW Agents Server

API REST desenvolvida com Fastify para o projeto NLW Agents.

## 🛠️ Tecnologias

- **Runtime**: Node.js com TypeScript
- **Framework**: Fastify
- **Database**: PostgreSQL com pgvector
- **ORM**: Drizzle ORM
- **Validação**: Zod
- **Linter**: Biome
- **Containerização**: Docker

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts
│   ├── migrations/
│   ├── schema/
│   │   ├── index.ts
│   │   └── rooms.ts
│   └── seed.ts
├── http/
│   └── routes/
│       └── get-rooms.ts
├── env.ts
└── server.ts
```

## 🚀 Setup

### Pré-requisitos

- Node.js 18+
- Docker e Docker Compose

### Instalação

1. Clone o repositório
2. Instale as dependências:
```bash
npm install
```

3. Configure as variáveis de ambiente:
```bash
# Crie um arquivo .env na raiz do projeto
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

4. Inicie o banco de dados:
```bash
docker-compose up -d
```

5. Execute as migrações:
```bash
npx drizzle-kit migrate
```

6. (Opcional) Popule o banco com dados iniciais:
```bash
npm run db:seed
```

### Desenvolvimento

```bash
npm run dev
```

### Produção

```bash
npm start
```

## 📋 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento com hot reload
- `npm start` - Inicia o servidor em modo produção
- `npm run db:seed` - Popula o banco de dados com dados iniciais

## 🔧 Padrões de Projeto

- **Arquitetura**: API REST com Fastify
- **Validação**: Schema validation com Zod
- **Database**: Migrations com Drizzle Kit
- **Type Safety**: TypeScript em todo o projeto
- **Code Style**: Biome para formatação e linting

## 🌐 Endpoints

- `GET /health` - Health check
- `GET /rooms` - Lista todas as salas

## 📊 Banco de Dados

- **PostgreSQL** com extensão pgvector
- **Schema**: Tabela `rooms` com campos: id, name, description, createdAt
- **Migrations**: Gerenciadas pelo Drizzle Kit 