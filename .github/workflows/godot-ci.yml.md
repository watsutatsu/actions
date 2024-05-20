## godot-ci

This workflow automatically builds and updates a Godot game for the web, then puts it online using Netlify. It ensures the game is always current with the latest changes and easily accessible.

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
    uses: watsutatsu/actions/.github/workflows/godot-ci.yml@main
    with:
      godot_version: 4.2.2
      export_name: test-project
      project_path: games/test-project
    secrets: inherit
```

## References
- https://github.com/watsutatsu/test-godot/pull/7
