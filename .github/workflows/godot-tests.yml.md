## godot-ci.yml.md

This workflow automatically downloads GUT and runs the test suite for a Godot game.

### Usage

```yaml
name: godot-tests

on:
  pull_request:
  push:
    branches:
      - main

jobs:
  godot-ci:
    uses: watsutatsu/actions/.github/workflows/godot-tests.yml@apaz/godot-tests-1
    with:
      gut_version: 9.2.1
      godot_version: 4.2.2
      project_path: games/main
```

## References
- https://github.com/watsutatsu/test-godot/pull/7
