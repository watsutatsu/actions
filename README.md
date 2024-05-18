# 🔧 base-actions
> Resuseable actions to use in other repositories

## Creating a Reusable Workflow

Reusable workflows in GitHub Actions allow you to define a set of actions once and call them from other workflows. This can save time and ensure consistency across your projects.

### Step 1: Define the Reusable Workflow

Create a new workflow file under the directory  [.github/workflows](./.github/workflows) . Let's call it `hello-world-reusable.yml`.

```yaml
# .github/workflows/hello-world-reusable.yml
name: Reusable Hello World Workflow

on:
  workflow_call:
    inputs:
      name:
        description: 'The name to greet'
        required: true
        default: 'World'
        type: string

jobs:
  say_hello:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v2

      - name: Say Hello
        run: echo "Hello, ${{ inputs.name }}!"
```
### Step 2: Call the Reusable Workflow

In another repository (or the same one), create another workflow file under `.github/workflows` and reference the reusable workflow.

```yaml
# .github/workflows/call-hello-world.yml
name: Call Reusable Hello World Workflow

on:
  push:
    branches:
      - main

jobs:
  call_hello_world:
    uses: your-username/your-repository/.github/workflows/hello-world-reusable.yml@main
    with:
      name: "GitHub Actions"

```

## Refereneces
- https://github.com/features/actions
- https://docs.github.com/en/actions
