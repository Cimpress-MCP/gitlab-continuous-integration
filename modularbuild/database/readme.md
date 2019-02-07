
# Testing Applications With Databases 

## Stages 

Include `databasestages.yaml` in your CI file for the required stages of a database service. 

## Build Testing Postgres Databases 

### Npm 

Extending your build with from `.buildDatabaseWithNpm` will flyway to set up a docker image containing a postgres database and use npm to run tests against it. 

#### Example

```yaml 
build:database:
  extends: .buildDatabaseWithNpm
  variables:
    POSTGRES_VERSION: postgres:10.6-alpine 
    POSTGRES_DB: postgres
    POSTGRES_USER: postgres
    POSTGRES_SERVER: postgres
    POSTGRES_PASSWORD: ''
```

