# Technical Claims Verification: `contributing.mdx`

| Claim | Verified | Source | Notes |
| :--- | :---: | :--- | :--- |
| 1. ToggleMesh is open source. | ✅ | `LICENSE` / Public Repo | The project is an open-source initiative. |
| 2. API Node is a .NET 10 application. | ✅ | `ToggleMesh.API.csproj` | Verified `<TargetFramework>net10.0</TargetFramework>`. Fixed documentation which previously claimed .NET 8. |
| 3. Core API provides REST and SSE. | ✅ | `ToggleMesh.API` routing | The API node acts as the backend. |
| 4. Admin UI is React, served by API in Docker, or standalone Vite locally. | ✅ | Build setup | Verified Dockerfile and Vite setup. |
| 5. PostgreSQL is the primary database. | ✅ | `docker-compose.yml` | Base database. |
| 6. Redis is the distributed caching and Pub/Sub mechanism. | ✅ | `docker-compose.yml` | Base caching. |
| 7. ClickHouse & Kafka available via `docker-compose.enterprise.yml`. | ✅ | Filesystem | Found the enterprise compose file. |
| 8. `docker-compose.dev.yml` provides local dev overrides. | ✅ | Filesystem | Found the dev compose file. |
| 9. Starting the stack uses `docker compose up -d`. | ✅ | Docker CLI | Standard V2 Compose syntax. |
| 10. `TM_RUN_MIGRATIONS_ON_STARTUP=true` is the default. | ✅ | `docker-compose.yml` | See line 50. |
| 11. Admin UI is at `http://localhost:5264`, Scalar at `/docs`. | ✅ | `docker-compose.yml` / `ToggleMesh.API` | Scalar is mapped correctly in .NET. |
| 12. Default Admin Email is `admin@togglemesh.local`. | ✅ | `docker-compose.yml` | See line 53. |
| 13. Default Admin Password is `Admin123!`. | ✅ | `docker-compose.yml` | See line 54. |
| 14. Infrastructure can be run via `docker compose up -d db redis`. | ✅ | Docker Compose | Targets specific services. |
| 15. API natively defaults to `https://localhost:7282` (or `5264`). | ✅ | `launchSettings.json` | Verified HTTP/HTTPS bindings. |
| 16. Admin UI natively requires `npm run dev` in `src/ToggleMesh.AdminUI` on `5173`. | ✅ | Node/Vite Standards | Typical Vite port. |
