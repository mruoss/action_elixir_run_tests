# Run Tests in latest Elixir Versions

## Usage as Re-Usable Workflow

```yaml
name: Code Quality
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
jobs:
  test:
    uses: mruoss/action_elixir_run_tests/.github/workflows/elixir-code-quality.yml@v2.1.0
    with:
      checkout: true
      with-kubernetes: false
      check-formatting: true
      run-credo: strict
      run-dialyzer: true
    secrets:
      token: ${{ secrets.GITHUB_TOKEN }}
```


```yaml
name: Elixir Compatibility Matrix
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
jobs:
  test:
    uses: mruoss/action_elixir_run_tests/.github/workflows/elixir-run-tests.yml@v2.1.0
    with:
      checkout: true
      warnings-as-errors: true
      with-kubernetes: false
      include-integration-tests: false
    secrets:
      token: ${{ secrets.GITHUB_TOKEN }}
```
