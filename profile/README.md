# Productify Framework

> Your team's toolkit to stop configuring and start innovating.

**[📚 Documentation](https://docs.productify.dev)** • **[🌐 Website](https://productify.dev)**

> **ℹ️ Private Repositories - Thesis Project**  
> These repositories are currently private as part of the thesis project "Building and adapting a software productization framework"

> **⚠️ Early Development**  
> Productify Framework is currently in early development stages. While functional, it may contain bugs and undergo breaking changes. Use with caution in production environments and ensure thorough testing for your specific use cases.

## 🚀 Core Components

- **🎛️ [Manager](https://github.com/ProductifyFW/manager)** - Central control plane with GraphQL/REST APIs, multi-tenant resource management, ESB gateway, trigger system, and micro-frontend orchestration
- **⚡ [CLI](https://github.com/ProductifyFW/cli)** - Developer toolkit for project initialization, resource management, and automatic semantic versioning
- **🔄 [Autoscaler](https://github.com/ProductifyFW/autoscaler)** - Application scaling with Prometheus metrics and HashiCorp Nomad integration
- **🌐 [Proxy](https://github.com/ProductifyFW/proxy)** - Caddy-based reverse proxy with application routing and authentication

## 🎯 Key Features

### Multi-Tenancy by Design

Hierarchical Project → Tenant → Application structure with complete data isolation and flexible configuration layers. Evolving toward **single deployment, multi-app, multi-tenant**: applications defined once and enabled per tenant, first-class environments, and one proxy instance serving every app and tenant (see Roadmap).

### Enterprise Service Bus (ESB)

Secure API gateway with Go template-based message transformation, configurable audit logging and machine user authentication.

### Trigger System

Cron-based scheduling with backend HTTP callbacks, distributed execution with database-level locking and Prometheus metrics.

### Configuration Management

JSON-based settings with Project/Tenant/Application layers, separate frontend/backend configurations, and real-time updates.

### Micro-Frontend Architecture

Pilet management with versioning, dynamic module discovery via feed service, and Piral shell integration.

## 🛠️ Technology Stack

**Backend**: Go (Manager, CLI, Autoscaler) • **Frontend**: Vue 3 + TypeScript (Manager UI), framework-agnostic integration libraries • **Database**: PostgreSQL • **API**: GraphQL + REST • **Proxy**: Caddy • **Orchestration**: Nomad • **Metrics**: Prometheus • **Autoscaling**: SARIMAX forecasting + MILP optimization (Python)

## 🤝 Use Cases

- **SaaS Platforms** - Multi-tenant applications with isolation and per-tenant configuration
- **Enterprise Applications** - RBAC, audit logging, modular feature delivery
- **API Gateways** - Secure external access with transformation and audit trails
- **Multi-Brand Platforms** - Multiple brands with tenant-specific configurations

## 🗺️ Roadmap (2026)

Planned across the workspace (sequenced, security first):

- **Security hardening release** — proxy header sanitization, proxy↔manager shared secret, signed tenant cookies with membership checks, PAT application scoping, resolver authorization fixes
- **Single deployment, multi-app, multi-tenant** — applications decoupled from tenants (defined once, enabled per tenant), tenants as customer organizations, first-class environments, Manager-rendered proxy config pushed via Caddy's admin API
- **Official Go server library** — `net/http` core + Gin adapter in be-integrations, protocol parity with the Node SDK, `managertest` test fake
- **Self-service & roles** — configurable tenant roles over a fixed permission vocabulary, delegated tenant administration, invitation flow, opt-in role/permission forwarding to apps
- **Developer experience** — `pfy dev` one-command local platform with idempotent seeding, official dev shims and test fakes, identity-injecting dev proxy
- **Generated deployments** — Nomad jobs, autoscaler policies, and the entire Caddyfile rendered from specs with drift detection; versioned self-hosted install bundle
- **Later** — Kubernetes support, deep-learning autoscaling, micro-frontend (pilet) finalization, compliance/audit tooling

## 📜 License

MIT License (Manager, CLI, Autoscaler) • Apache 2.0 (Proxy/Caddy derivative)

## 🔗 Resources

- **[Documentation](https://docs.productify.dev)** - Guides and API reference
- **[Frontend Integrations](https://github.com/ProductifyFW/fe-integrations)** - Frontend libraries, components and Piral integration helpers
- **[Backend Integrations](https://github.com/ProductifyFW/be-integrations)** - Node.js/Express middleware and library; official Go library planned (see Roadmap)
