# workflows

Reuseable GitHub Actions Workflows

## Typical workflow for `pnpm` projects

```yaml
name: On Push

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
    uses: bjerkio/workflows/.github/workflows/pnpm-typical.yml@v1
```

See [pnpm-typical.yml](pnpm-typical.yml) for more details.
