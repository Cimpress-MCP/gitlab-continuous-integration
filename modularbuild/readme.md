
## Abstract Components

Reusable components for deployment and/or data migration. 

### Migrate 
  Base instructions used for data migration per environment using flyway and Postgres.  
#### Example
```yaml 
  migrate-int:
  extends: .migrate
  stage: migrate-int
```

### Deploy

Contain an [extensible abstract](https://docs.gitlab.com/ee/ci/yaml/#extends) `.deploy` for tasks specifically for deploying the service.
  
#### Example
```yaml 
deploy-int:
  extends: .deploy
  stage: deploy-int
  variables:
    CI_ENVIRONMENT_NAME: integration
```

### Database node application 

Extending your build with from `.testNodeApplicationWithDatabase` with flyway to set up a docker image containing a postgres database and use npm to run tests against it. 

#### Example

```yaml 
build:database:
  extends: .testNodeApplicationWithDatabase
  variables:
    POSTGRES_VERSION: postgres:10.6-alpine 
    POSTGRES_DB: postgres
    POSTGRES_USER: postgres
    POSTGRES_SERVER: postgres
    POSTGRES_PASSWORD: ''
```

