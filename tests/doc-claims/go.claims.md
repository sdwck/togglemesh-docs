# Claims: go.mdx

- **[CLAIM-SDK-GO-001]** Import path is `github.com/sdwck/ToggleMesh/sdks/go/togglemesh`.
- **[CLAIM-SDK-GO-002]** Client constructor uses functional options: `togglemesh.NewClient(togglemesh.WithBaseURL(...), togglemesh.WithAPIKey(...))`.
- **[CLAIM-SDK-GO-003]** Graceful shutdown uses `defer client.Close()`.
- **[CLAIM-SDK-GO-004]** Flag evaluation uses `client.IsEnabled(flagKey, options...)`.
- **[CLAIM-SDK-GO-005]** Package includes CLI code generator executable `github.com/sdwck/ToggleMesh/sdks/go/cmd/togglemesh`.
