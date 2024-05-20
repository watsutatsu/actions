# godot-tests

This workflow automatically downloads GUT (Godot Unit Test) and runs the test suite for a Godot game. It is designed to streamline the process of continuous integration (CI) for your Godot projects by ensuring that your tests are run automatically whenever changes are pushed or pull requests are opened.

### Prerequisites

Before using this workflow, ensure that:
- You have a Godot project with a test suite configured using GUT.
- Your repository is set up with the necessary directories and files for running Godot and GUT.

### Basic Usage

To use this workflow in your GitHub Actions, create a file named `.github/workflows/godot-tests.yml` in your repository with the following content:

```yaml
name: godot-tests

on:
  pull_request:
  push:
    branches:
      - main

jobs:
  godot-ci:
    uses: watsutatsu/actions/.github/workflows/godot-tests.yml@main
```

### Customizing the Workflow

You can customize the workflow by passing parameters to fit your project's specific requirements. Here are some of the parameters you can use:

- **`gut_version`**: Specify the version of GUT to use for running your tests. Ensure that this version is compatible with your Godot version.
- **`godot_version`**: Specify the version of Godot to use for running your project and tests.
- **`project_path`**: Specify the relative path to your Godot project within the repository.

Here is an example of a customized workflow configuration:

```yaml
name: godot-tests

on:
  pull_request:
  push:
    branches:
      - main

jobs:
  godot-ci:
    uses: watsutatsu/actions/.github/workflows/godot-tests.yml@main
    with:
      gut_version: 9.2.1
      godot_version: 4.2.2
      project_path: games/main
```

### Conclusion

Using this CI workflow ensures that your Godot project's tests are automatically executed on every push or pull request, helping you catch issues early and maintain code quality.

## References

- [Godot Unit Test (GUT) Documentation](https://github.com/bitwes/Gut)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Example Pull Request using this workflow](https://github.com/watsutatsu/test-godot/pull/7)