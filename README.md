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

## Inputs
```yml
package_json_path:
  description: 'the path to the package.json file to read the version from'
  required: false
  default: './package.json'
github_token:
  description: 'GitHub token with permissions to create releases.'
  required: true
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
