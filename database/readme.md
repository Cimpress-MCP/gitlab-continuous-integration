
# Testing Databases 

## Stages 

Include `stages.yaml` in your CI file for the required stages of a database service. 

## Build Testing Postgres Databases 

### Npm 

Extending your build with from `.buildDatabaseWithNpm` will use npm with flyway to set up a docker image containing a postgres database that your tests can run against. 

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

