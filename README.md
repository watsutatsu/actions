# :godmode: base-actions
> Resuseable actions to use in other repositories


## Examples

### Creating a reuseable workflow

Create a new workflow file under [.github/workflows](./github/workflows) 

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

In another repository create another  workflow file under `.github/workflows` and reference this repository

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
