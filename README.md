# go-mod-tidy-workflow

GitHub Actions Reusable Workflow to run `go mod tidy` and push a commit

## How to use

```yaml
---
name: go mod tidy
on:
  pull_request:
    paths:
      - go.mod
      - go.sum
      - "**.go"
permissions: {}
jobs:
  go-mod-tidy:
    uses: suzuki-shunsuke/go-mod-tidy-workflow/.github/workflows/go-mod-tidy.yaml@main
    with:
      go-version: 1.20.2
      aqua_version: v1.35.0
    secrets:
      gh_app_id: ${{secrets.APP_ID}}
      gh_app_private_key: ${{secrets.APP_PRIVATE_KEY}}
    permissions:
      contents: read
```

## Requirements

- ghcp

```sh
aqua g -i int128/ghcp
```

## LICENSE

[MIT](LICENSE)
