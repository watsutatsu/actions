## godot-export

This workflow builds and exports a Godot Project.

### Usage

To use this workflow, add the following configuration to your GitHub Actions workflow file. This configuration triggers the workflow on both pull requests and pushes to the `main` branch.

```yaml
name: godot-tests

on:
  pull_request:
  push:
    branches:
      - main

jobs:
  godot-ci:
    uses: watsutatsu/actions/.github/workflows/godot-export.yml@main
```

### Customizing the Workflow

You can customize the workflow by passing parameters to fit your project's specific requirements. Here are some of the parameters you can use:

- **`gut_version`**: Specify the version of GUT (Godot Unit Test) to use for running your tests. Ensure that this version is compatible with your Godot version.
- **`godot_version`**: Specify the version of Godot to use for running your project and tests. This ensures that the correct runtime and features are used during the build and export process.
- **`project_path`**: Specify the relative path to your Godot project within the repository. This tells the workflow where to find your project's main files.

Here is an example of a customized workflow configuration:

```yaml
name: Build and Deploy

on:
  pull_request:
  push:
    branches:
      - main

jobs:
  godot-ci:
    uses: watsutatsu/actions/.github/workflows/godot-export.yml@main
    with:
      godot_version: 4.2.2
      project_path: games/test-project
```

## References
- [GitHub Pull Request #7](https://github.com/watsutatsu/test-godot/pull/7)