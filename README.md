# go-mod-tidy-workflow

GitHub Actions Reusable Workflow to run `go mod tidy` and push a commit. Keep go.mod and go.sum clean!

![image](https://user-images.githubusercontent.com/13323303/223891482-2495d7c5-6d92-483d-82cc-9275038c9b7e.png)

--

![image](https://user-images.githubusercontent.com/13323303/223891658-0594823a-8a26-4bc5-b3ea-3a804d6923b1.png)

[Workflow](.github/workflows/go-mod-tidy.yaml)

Please see [go-mod-tidy-action](https://github.com/suzuki-shunsuke/go-mod-tidy-action) too!

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
    uses: suzuki-shunsuke/go-mod-tidy-workflow/.github/workflows/go-mod-tidy.yaml@dd0258320254eb20e317fb41f08ba16c754f8ffa # v0.1.0
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
