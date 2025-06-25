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
