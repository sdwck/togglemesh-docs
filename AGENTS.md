# AGENTS.md: ToggleMesh Documentation Context

**Target Audience:** AI Agents (Cursor, Claude, Copilot).
**Purpose:** Contextual map for the `docs.togglemesh.dev` repository and its relation to the broader `ToggleMesh` ecosystem. Follow these constraints when generating or modifying documentation.

## 1. Ecosystem Map

| Project | Path | Role | Core Tech Stack |
|---|---|---|---|
| **API** | `Solutions/ToggleMesh` | Control & Data Plane | .NET 10, FastEndpoints, PostgreSQL, Redis, Kafka, ClickHouse |
| **Admin UI** | `Solutions/ToggleMesh/src/ToggleMesh.AdminUI` | Dashboard & Management | React (Vite), TailwindCSS, Zustand |
| **Landing** | `Solutions/togglemesh.dev` | Marketing | Next.js 15, Tailwind v4, GSAP, R3F (WebGL) |
| **Docs** | `Solutions/docs.togglemesh.dev` | Dev Documentation | Next.js, Fumadocs, MDX, Shiki |
| **SDKs** | `Solutions/ToggleMesh/sdks` | Polyglot Clients | C#, Python, Go, Node.js, JS/React, UE5, CLI |

## 2. Source of Truth (Cross-Reference Targets)

When authoring documentation, extract absolute technical truths (avoid hallucinating configurations) from these critical files in the `Solutions/ToggleMesh` directory:

*   **`README.md`**: Baseline architecture diagrams, performance limits (<30ns latency, 0 bytes allocated), feature matrix, and `docker-compose` commands.
*   **`src/ToggleMesh.API/Program.cs`**: Backend infrastructure.
    *   Verify: Rate Limiters, Background Channels (`MetricsWorker`, `WebhookDispatcherService`), Auth schemas (JWT, PAT), SSE Configuration, Quartz jobs.
*   **`src/ToggleMesh.AdminUI/src/router.tsx`**: UI feature mapping.
    *   Verify routes: `/flags`, `/environments`, `/experiments`, `/audit`, `/terminal`, `/playground`.
*   **`sdks/` directory**: Native SDK implementations.
    *   `dotnet/`: Check `ref struct` usage and `HttpContext` DI injection.
    *   `js-cli/`: Check CLI commands (`togglemesh config`, `togglemesh sync`).
*   **`benchmarks/` directory**: Performance and load testing.
    *   `ToggleMesh.Benchmarks/`: Microbenchmarks for the zero-allocation evaluation engine (BenchmarkDotNet).
    *   `ToggleMesh.LoadTests/`: API throughput and channel ingestion tests (k6 or similar).

## 3. Documentation Architecture (`docs.togglemesh.dev`)

- **Framework**: Next.js + Fumadocs MDX
- **Content Root**: `content/docs/`
- **Nav Configuration**: `content/docs/meta.json`

### Required Content Structure:
- `getting-started/`: Quickstart, Docker Compose (Core vs Enterprise stack).
- `architecture/`: Data Plane vs Control Plane, Zero-alloc Engine, SSE Push, MAB/ClickHouse analytics.
- `sdks/`: Implementation guides per language (Install, Init, Evaluate, Track).
- `admin-ui/`: User guides for Flags, Targeting, Segments, Audit Logs.
- `api-reference/`: Keep manual REST API documentation minimal (ToggleMesh exposes automated OpenAPI via Scalar). 

## 4. AI Authoring Guidelines
- **Tone:** Technical, precise, highly pragmatic. No marketing fluff.
- **Code Snippets:** Prefer C# and TypeScript examples. Ensure exact variable matches with the actual SDK code. 
- **Context Limits:** Do not hallucinate API endpoints; if an endpoint is missing from context, request the `Program.cs` or Endpoint class file.
- **Images:** When writing content, if you believe an image (diagram, UI screenshot, or architecture flow) would enhance the explanation, add a markdown comment in this format: `{/* TODO: Image - [Description of what the image should show] */}`. This helps human maintainers easily locate and insert the right visual assets later. Use MDX comment syntax, NOT HTML comments, to prevent build errors.
- **Mandatory Fact-Checking:** Before generating or modifying ANY documentation page, you MUST verify the technical facts directly in the source code (using `grep_search`, `view_file`, etc.). You MUST write down these facts in a temporary `fact_check.md` artifact (or directly within the active `task.md`) before generating the documentation content. NEVER hallucinate features that are "on the roadmap" but not yet in the codebase (e.g., Numeric flags). Always map the documentation strictly to the current reality of the repository.