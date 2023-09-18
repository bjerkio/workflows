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
    uses: bjerkio/workflows/.github/workflows/pnpm-typical.yml@v2
```

You can set `use-engines: true` to use `"engines"` from `package.json` for Node version.

See [pnpm-typical.yml](.github/workflows/pnpm-typical.yml) for more details.

## Typical workflow for `bun` projects

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
    uses: bjerkio/workflows/.github/workflows/bun-typical.yml@v1
```

See [bun-typical.yml](.github/workflows/bun-typical.yml) for more details.

_Note_: [Bun does not currently support `--if-present`][bun-if-present-issue], so you need to make sure that the scripts `lint`, `format`, `test` and `build` are present in `package.json`.
If you are not using all of them, they can be skipped by adding a `exit 0` command
to `"scripts"`.

Example:

```jsonc
{
  // ...
  "scripts": {
    "build": "echo 'not implemented'; exit 0;",
    "lint": "echo 'not implemented'; exit 0;",
    "format": "echo 'not implemented'; exit 0;",
    "test": "echo 'not implemented'; exit 0;"
  }
}
```

[bun-if-present-issue]: https://github.com/oven-sh/bun/issues/5670
