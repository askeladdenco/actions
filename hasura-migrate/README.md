# hasura-migrate

Migrates a Hasura database

## Parameters

| **Input**           | **Description**                                  | **Required** | **Default** |
|---------------------|--------------------------------------------------|--------------|-------------|
| `endpoint`          | Endpoint of the Hasura instance                  | true         | -           |
| `database-name`     | Name of the database to migrate                  | true         | -           |
| `admin-secret`      | Admin secret of the Hasura instance              | true         | -           |
| `cli-version`       | Hasura CLI version                               | false        | v2.1.1      |
| `working-directory` | Working directory where hasura config is located | false        | .           |

## Example usage

```yaml
name: Migrate hasura 
on:
  push:
    branches:
      - master
jobs:
  install:
    runs-on: ubuntu-latest
    steps:
      - uses: askeladdenco/actions/hasura-migrate@v0.0.1
        with:
          endpoint: https://hasura.swash.no
          database-name: default
          admin-secret: ${{ secrets.HASURA_ADMIN_SECRET }}
```
