# Deploy 

## Deploy Components

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

Base instructions used for deployment. 
  
#### Example
```yaml 
deploy-int:
  extends: .deploy
  stage: deploy-int
```

## Bean Stalk 

Sets up a pipeline targeted for elastic beanstalk deployment. 

Add `beanstalkdeploy.yaml` to includes to use this feature. This file has a dependency on `deploycomponents.yaml` which must be included as well. 

