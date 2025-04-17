# Run Tests in latest Elixir Versions

## Usage as Re-Usable Workflow

```yaml
name: Caller Workflow
on: [push]
jobs:
  call-reusable:
    uses: mruoss/action_elixir_run_tests/.github/workflows/elixir-run-tests@main
    with:
      input1: "Hello from caller"
```
