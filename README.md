# release-tag-package.json
> creates a release and a tag from the package.json using github releases

## Pre-requisites
The following actions need to be in scope
- actions/checkout@v4
- actions/setup-node@v4

## Permissions
```yml
permissions:
  contents: write
```


## Example workflow
```yml
name: Release form package job
on:
  push:
    branches:
      - main

permissions:
  contents: write
  
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: release
        uses: jpbnetley/release-tag-package.json@main
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}

```

## Ref
https://github.com/jpbnetley/test-release-tag-package.json
