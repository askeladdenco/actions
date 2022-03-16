# yarn-install

Installs dependencies with yarn (including private dependencies)

## Parameters

| **Input**         | **Description**                | **Required** | **Default** |
|-------------------|--------------------------------|--------------|-------------|
| `node-version`    | Node version to use            | true         | -           |
| `auth-token`      | GitHub authentication token    | true         | -           |
| `install-command` | Command to install the project | false        | yarn        |
| `cache`           | What to cache                  | false        | yarn        |

## Example usage

```yaml
name: Install 
on:
  push:
    branches:
      - master
jobs:
  install:
    runs-on: ubuntu-latest
    steps:
      - uses: askeladdenco/actions/yarn-install@v0.0.1
        with:
          node-version: 16.13.0
          auth-token: ${{ secrets.ACO_NPM_AUTH_TOKEN }}
          install-command: yarn --cwd packages/some_api
```
