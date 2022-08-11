# yarn-install

Installs dependencies with yarn (including private dependencies)

## Parameters

| **Input**         | **Description**                                                                                         | **Required** | **Default** |
| ----------------- | ------------------------------------------------------------------------------------------------------- | ------------ | ----------- |
| `auth-token`      | GitHub authentication token                                                                             | false        | -           |
| `marmelab-token`  | Auth token for marmelab registry (react-admin)                                                          | false        | -           |
| `node-version`    | Node version to use                                                                                     | false        | 16.13.0     |
| `install-command` | Command to install the project                                                                          | false        | yarn        |
| `cache`           | What to cache                                                                                           | false        | yarn        |
| `npmrc-paths`     | Relative paths to where npmrc files should be placed (space separated). Only required for heroku deploy | false        | -           |

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
          install-command: yarn --cwd packages/api
          npmrc-paths: . ./packages/api
```
