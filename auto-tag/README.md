# auto-tag

Automatically tags and adds release to the repo based on semantic commits

## Parameters

| **Input**         | **Description**                    | **Required** | **Default** |
|-------------------|------------------------------------|--------------|-------------|
| `github_token`    | GitHub token with repo permissions | true         | -           |

## Example usage

```yaml
name: Bump version
on:
  push:
    branches:
      - master
jobs:
  tag:
    runs-on: ubuntu-latest
    steps:
      - uses: askeladdenco/actions/auto-tag@master
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}

```
