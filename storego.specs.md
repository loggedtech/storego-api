# STOREGO - Documento de Especificação de Requisitos

## 1. INTRODUÇÃO

### 1.1 Propósito do Documento

Este documento estabelece a especificação completa de requisitos para o sistema **StoreGo**, uma plataforma SaaS multi-organizacional para gestão empresarial integrada com controle de assinaturas, gamificação e gestão de força de campo.

### 1.2 Escopo do Sistema (6 Módulos + Super Administrador)

| Módulo | Descrição | Prioridade |
|--------|----------|------------|
| **Módulo de Tarefas** | Gestão de tarefas, equipes, projetos, visualizações | Must |
| **Módulo de Temperatura** | Equipamentos, ambientes, veículos, alertas | Must |
| **Módulo de Gestão de Ativos** | Cadastro, inventário, auditoria, baixa | Must |
| **Módulo de Manutenção** | Ordens de serviço com workflow de aprovação, SLA, custos | Should |
| **Módulo de Assinaturas** | Gestão de planos, cobranças, gamificação | Must |
| **Módulo de Força de Campo** | Presença de promotores, escalas, dashboard | Must |
| **Super Administrador** | Gestão global do sistema | Must |

### 1.3 Diagrama de Contexto do Sistema

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                           SISTEMA STOREGO                           │
│  ┌─────────────────────────────────────────────────────────────────┐  │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐       │  │
│  │  │ Módulo   │  │ Módulo   │  │ Módulo   │  │ Módulo   │       │  │
│  │  │ Tarefas  │  │Temperatura│  │ Ativos   │  │Manutenção│       │  │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘       │  │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐                      │  │
│  │  │ Módulo   │  │ Módulo   │  │ Super    │                      │  │
│  │  │Assinaturas│  │Campo     │  │ Admin    │                      │  │
│  │  └──────────┘  └──────────┘  └──────────┘                      │  │
│  └─────────────────────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────┘
```

### 1.4 Atores Externos

| Ator | Descrição | Tipo |
|------|-----------|------|
| **Usuário Administrador** | Gerencia organização | Primário |
| **Usuário Gestor** | Cria projetos | Primário |
| **Promotor de Campo** | Realiza check-in | Primário |
| **Sensor IoT** | Envia temperatura | Sistema |
| **Stripe** | Pagamentos | Sistema |

### 1.5 Restrições do Projeto

| Aspecto | Definição |
|---------|----------|
| Prazo | 3 meses |
| Equipe | 1-2 desenvolvedores |
| Ambientes | Dev, Homologação, Produção |

---

## 2. STACK TECNOLÓGICA

### 2.1 Visão Geral

| Camada | Tecnologia |
|--------|------------|
| Runtime | Bun |
| Backend | Elysia + TypeScript |
| Frontend | React + TypeScript |
| Banco de Dados | PostgreSQL |
| ORM | Drizzle ORM |
| Cache | Redis |
| Armazenamento | AWS S3 |
| Gateway de Pagamento | Stripe |
| Linting | Biome |
| Logging | Pino |

---

*Versão do Documento: 1.1*  
*Última Atualização: 2026-04-23*  
*Autor: Equipa Técnica StoreGo*