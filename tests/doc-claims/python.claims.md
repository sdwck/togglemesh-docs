# Claims: python.mdx

- **[CLAIM-SDK-PY-001]** Package name is `togglemesh`.
- **[CLAIM-SDK-PY-002]** Client constructor accepts `ToggleMeshOptions(base_url=..., server_key=...)`.
- **[CLAIM-SDK-PY-003]** Evaluation methods include: `is_enabled`, `get_variation`, `get_json`, `track`.
- **[CLAIM-SDK-PY-004]** Background threads shutdown method is `client.stop()` or `client.close()`.
- **[CLAIM-SDK-PY-005]** Python package includes native CLI code generator wrapper `togglemesh/cli.py`.
- **[CLAIM-SDK-PY-006]** CLI wrapper automatically downloads the OS-specific compiled `ToggleMesh.CLI` binary from GitHub Releases.
- **[CLAIM-SDK-PY-007]** CLI sync command format: `togglemesh sync -l python -o ./flags.py`.
