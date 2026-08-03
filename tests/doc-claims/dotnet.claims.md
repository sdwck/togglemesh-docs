# Claims: dotnet.mdx

- **[CLAIM-SDK-NET-001]** Package name is `ToggleMesh.SDK`.
- **[CLAIM-SDK-NET-002]** Client registration method is `builder.Services.AddToggleMeshClient(...)`.
- **[CLAIM-SDK-NET-003]** `AddToggleMeshHttpContext()` enables automatic user context extraction from ASP.NET Core ambient HttpContext.
- **[CLAIM-SDK-NET-004]** Evaluation methods include: `IsEnabled`, `GetStringVariation`, `GetJsonVariation`, `Track`.
- **[CLAIM-SDK-NET-005]** `[ToggleMeshContext]` attribute uses C# Source Generators to create zero-allocation evaluation contexts.
