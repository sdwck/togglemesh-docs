# Claims: dotnet.mdx

- **[CLAIM-SDK-NET-001]** Package name is `ToggleMesh.SDK`.
- **[CLAIM-SDK-NET-002]** Client registration method is `builder.Services.AddToggleMeshClient(options => ...)`.
- **[CLAIM-SDK-NET-003]** `AddToggleMeshHttpContext()` enables automatic user context extraction from ASP.NET Core ambient HttpContext.
- **[CLAIM-SDK-NET-004]** Evaluation methods include: `IsEnabled`, `GetStringVariation`, `GetJsonVariation`, `Evaluate`, and `Track`.
- **[CLAIM-SDK-NET-005]** `[ToggleMeshContext]` attribute uses C# Source Generators to generate an `IContextAccessor` implementation for zero-allocation struct-based evaluation contexts.
- **[CLAIM-SDK-NET-006]** `ToggleMeshUser<TContext>` struct supports pass-by-reference (`ref`) zero-allocation flag evaluation and event tracking.
- **[CLAIM-SDK-NET-007]** Uses a persistent SSE (Server-Sent Events) connection to the ToggleMesh API for real-time flag updates.
- **[CLAIM-SDK-NET-008]** Flag evaluations are performed completely in-memory, requiring no network calls (zero-latency lookups).
- **[CLAIM-SDK-NET-009]** The CLI (`togglemesh sync`) generates a `Flags` static class with strongly-typed `public const string` constants for flag keys.
- **[CLAIM-SDK-NET-010]** `IToggleMeshClient` is registered and injected as a Singleton and implements `IHostedService` for automatic background startup/lifecycle management.
- **[CLAIM-SDK-NET-011]** Supports offline resilience using a local JSON fallback file (`UseFallbackFile`, `FallbackFilePath`) when the API is unreachable.
- **[CLAIM-SDK-NET-012]** Supports tracking conversion events via `Track(...)` with optional numeric values and custom event properties (`TProperties`).
- **[CLAIM-SDK-NET-013]** `GetJsonVariation<T>` deserializes JSON flag payloads into strongly-typed C# objects directly.
- **[CLAIM-SDK-NET-014]** Configurable in-memory buffers: `AnalyticsChannelCapacity` (default 10,000), `MetricsBufferCapacity` (default 10,000), and `MaxBatchSize` (default 2,000).
- **[CLAIM-SDK-NET-015]** `Evaluate(...)` returns a `Guid?` representing the selected variation ID or rule evaluation ID.
