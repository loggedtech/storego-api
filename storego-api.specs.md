# STOREGO API - Especificação Técnica do Backend

## 1. VISÃO GERAL DO BACKEND

### 1.1 Objetivos
- API REST robusta e escalável para sistema SaaS multi-organizacional
- Aplicação monolith com Clean Architecture
- Suporte multi-tenant com isolamento por organização
- Alta performance com Bun runtime

### 1.2 Stack Tecnológica

| Camada | Tecnologia |
|--------|------------|
| Runtime | Bun |
| Framework | Elysia.js + TypeScript |
| ORM | Drizzle ORM |
| Banco de Dados | PostgreSQL |
| Cache | Redis |
| Validação | Zod |
| Autenticação | JWT + OAuth (Google) |
| Pagamentos | Stripe |
| Armazenamento | AWS S3 |
| Container | Docker |

---

## 2. ARQUITETURA - CLEAN ARCHITECTURE

### 2.1 Estrutura de Pastas

```
src/
├── domain/                          # CAMADA DE DOMÍNIO
│   ├── entities/                    # Entidades de negócio
│   ├── value-objects/            # Objetos de valor imutáveis
│   ├── repositories/             # Interfaces dos repositórios
│   ├── events/                   # Eventos de domínio
│   └── services/                 # Serviços de domínio
│
├── application/                  # CAMADA DE APLICAÇÃO
│   ├── commands/                # Commands (CQRS - Escrita)
│   ├── queries/                 # Queries (CQRS - Leitura)
│   ├── handlers/                 # Handlers
│   ├── dtos/                    # DTOs Input/Output
│   └── services/               # Serviços de aplicação
│
├── infrastructure/             # CAMADA DE INFRAESTRUTURA
│   ├── repositories/          # Implementações Drizzle
│   ├── database/              # Configuração e schema
│   ├── services/              # Serviços externos
│   └── event-handlers/
│
├── presentation/             # CAMADA DE APRESENTAÇÃO
│   ├── routes/             # Rotas Elysia
│   ├── controllers/
│   ├── middleware/
│   └── adapters/
│
├── config/                 # Configuração
├── shared/                 # Código compartilhado
├── tests/                 # Testes
└── index.ts               # Entry point
```

---

*Versão do Documento: 1.1*  
*Última Atualização: 2026-04-23*  
*Autor: Equipa Técnica StoreGo*