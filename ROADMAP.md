# ToggleMesh Documentation Roadmap (`docs.togglemesh.dev`)

This roadmap defines the comprehensive content plan for the ToggleMesh documentation portal. It incorporates all features, SDKs, competitive advantages (vs. LaunchDarkly, PostHog, Unleash), and deep architectural insights.

---

## Phase 1: Core Fundamentals & Onboarding

- **Introduction & Vision**
  - What is ToggleMesh?
  - Competitive Matrix: Why ToggleMesh? (Self-hosted, Zero-Alloc, Privacy-First, Built-in MAB).
- **Quickstart Guide**
  - 5-minute setup: Docker Compose (Core) + Interactive Multi-Language Evaluation.
  - *Enterprise UX*: Use Fumadocs `<Tabs>` to instantly switch code snippets between C#, Python, Node.js, Go, and React.
- **Core Concepts**
  - Projects, Environments, and API Keys.
  - Flags (Boolean vs Multivariate).
  - Target Rules & Segments.
  - Context & Identity Pseudonymization.
- **Migrating to ToggleMesh**
  - *Migration Guides*: `Migrating from LaunchDarkly`, `Migrating from Statsig`.
  - *Terminology Map*: Translating terms (e.g., LD "Segments" -> TM "Target Rules", LD "Context" -> TM "ToggleMeshUser").

---

## Phase 2: Architecture Deep Dives

- **Control Plane vs. Data Plane**
  - High-level architecture (API, UI, SDKs, PostgreSQL, Redis).
- **Evaluation Engine (Zero-Allocation & Custom Operators)**
  - Deep dive into the .NET SDK: `<30ns` latency, `0 bytes` allocated via `ref struct` and Expression Trees.
  - **Advanced Use Cases**: Creating *Custom Targeting Operators*. Learn how to implement `IRuleOperator` and register it in DI.
- **Real-Time Sync (SSE Push)**
  - Replacing HTTP polling with Server-Sent Events (SSE).
  - Redis Pub/Sub fan-out invalidation.
- **Offline Resilience**
  - SDK local JSON fallback mechanisms during network partitions.

---

## Phase 3: Self-Hosting & Enterprise Operations

- **Deployment Models**
  - **ToggleMesh Cloud (`app.togglemesh.dev`)**: The fully managed, zero-setup SaaS option. Currently free with fair-use limits.
  - **Core Stack**: PostgreSQL + Redis (Standard).
  - **Enterprise Stack (Kafka + ClickHouse)**: Kafka as a high-throughput ingest buffer (100k+ RPS). ClickHouse as the OLAP engine for Bayesian MAB aggregations.
- **Database Partitioning Strategy**
  - The `PartitioningWorker` (Quartz job) that auto-creates monthly partitions (`AuditLogs_yyyy_MM`). Zero-cost retention policies (dropping partitions).
- **Security & Compliance (GDPR-Ready)**
  - Role-Based Access Control (RBAC) & Two-Factor Auth.
  - Data privacy: 100% of PII stays in the VPC. Hashed identities via `IdentityHasher`.
  - GDPR erasure API & Immutable audit logs.
- **Troubleshooting & FAQ (Operations)**
  - *Reverse Proxy Issues*: Nginx/Traefik/Cloudflare configurations to prevent SSE connection drops and timeouts.
  - *Database Locks*: What to do if Postgres partitions fail to create.
  - *Network Partitions*: Validating that SDKs correctly hydrate from local JSON fallbacks.
- **Observability**
  - OpenTelemetry integrations (Metrics & Traces).
  - Performance benchmarks (`ToggleMesh.Benchmarks`, `ToggleMesh.LoadTests`).
- **Integrations & Webhooks**
  - Slack & MS Teams alerts.
  - SSRF-protected dispatcher with Polly DLQs.

---

## Phase 4: Feature Management (Admin UI)

- **Flag Management**
  - Creating and typing Multivariate Flags (JSON, String, Numeric).
  - Feature workflows and Change Approvals (Four-eyes principle).
  - Scheduled rollouts and auto-rollbacks.
- **Targeting Engine**
  - Contextual Percentage Rollouts.
  - Advanced Operators: Regex, Date bounds, Semantic Versioning (SemVer).

---

## Phase 5: Experimentation, Analytics & Direct Data Access

- **Built-in A/B Testing**
  - Setting up variants, assigning metrics, evaluating statistical significance.
- **Multi-Armed Bandits (MAB)**
  - Bayesian inference engine (Monte Carlo via Beta distributions) auto-adjusting traffic to winning variants.
- **Data Integrity**
  - Sample Ratio Mismatch (SRM) detection (Chi-Square tests).
- **Direct Data Access (For Data Engineers)**
  - *Data Schema Reference*: Detailed schema for `AnalyticsExposures` and `AnalyticsTracks` tables in ClickHouse.
  - *Custom Querying*: Example SQL queries for extracting conversion funnels directly from raw data to export to Tableau/Superset.
- **Future Roadmap (Preview)**
  - Mutual exclusion groups, Metric guardrails, CUPED, Sequential testing.

---

## Phase 6: SDK Ecosystem References

Documentation for all supported native SDKs, focusing on Initialization, Evaluation, Context Injection, and Tracking.

- **Server SDKs (SSE Sync, Local Eval)**
  - `.NET (C#)` (Stable) - Focus on `HttpContext` auto-enrichment and `IRuleOperator` extensibility.
  - `Node.js` (Beta)
  - `Python` (Beta)
  - `Go` (MVP)
- **Client SDKs (Polling Sync, Remote/Local Eval)**
  - `Browser JS / React` (Beta) - React Hooks, real-time listener.
  - `Unreal Engine (C++)` (MVP) - *Offline-first rendering & Scene hydration.*
- **Tooling**
  - `ToggleMesh CLI` (`js-cli`): Using `togglemesh config` and `togglemesh sync` for generating type-safe constants.

---

## Phase 7: Contributing & Local Development

- **Local Setup**
  - Running the full stack (API + UI + ClickHouse + Kafka) locally via Docker Compose for development.
- **Repository Architecture**
  - Navigating the codebase: where to find EF Core migrations, MediatR CQRS handlers, background workers, and rule operators.
