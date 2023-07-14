# workflows

Reuseable GitHub Actions Workflows

## Typical workflow for `pnpm` projects

```yaml
name: Workflow

on:
  push:
    branches:
      - main
      - "[0-9]+.x"
    tags:
      - "*"

jobs:
  typical-workflow:
    name: Lint, format, test and build
    uses: bjerkio/workflows/pnpm-typical@v1
```

See [pnpm-typical.yml](pnpm-typical.yml) for more details.
