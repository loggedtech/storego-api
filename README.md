# StoreGo API

Backend API para o sistema StoreGo - Plataforma SaaS multi-organizacional para gestão empresarial.

## Stack Tecnológica

| Tecnologia | Descrição |
|------------|------------|
| Bun | Runtime JavaScript/TypeScript |
| Elysia.js | Framework HTTP |
| Drizzle ORM | ORM para PostgreSQL |
| PostgreSQL | Banco de dados relacional |
| Redis | Cache e sessões |
| Zod | Validação de dados |
| JWT | Autenticação stateless |
| Stripe | Pagamentos |
| Biome | Linting e formatação |
| Pino | Logging |

## Arquitetura

Projeto utiliza **Clean Architecture** com as seguintes camadas:

```
src/
├── domain/           # Entidades, Value Objects, Repositories interfaces
├── application/      # Commands, Queries, Handlers (CQRS)
├── infrastructure/   # Repositories, Database, Services
├── presentation/    # Routes, Controllers, Middleware
├── config/          # Configurações
├── shared/         # Utilitários
└── tests/          # Testes
```

## Começando

### Instalação

```bash
# Instalar dependências
bun install

# Configurar variáveis de ambiente
cp .env.example .env

# Executar migrações
bun run db:migrate

# Iniciar servidor
bun run dev
```

### Variáveis de Ambiente

Consulte `.env.example` para todas as variáveis necessárias.

## Documentação

- [Especificação Técnica](./storego-api.specs.md)
- [Requisitos](./storego.specs.md)

## Licença

MIT