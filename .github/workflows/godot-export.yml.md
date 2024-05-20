## godot-export

This workflow builds and exports a Godot Project

### Usage

```yaml
name: Build and Deploy

on:
  pull_request:
  push:
    branches:
      - main

permissions:
  pull-requests: write

jobs:
  godot-ci:
    uses: watsutatsu/actions/.github/workflows/godot-exoprt.yml@main
    with:
      godot_version: 4.2.2
      export_name: test-project
      project_path: games/test-project
    secrets: inherit
```

## References
- https://github.com/watsutatsu/test-godot/pull/7
