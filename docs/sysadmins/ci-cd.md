# CI/CD

We use CircleCI to manage Continuous Integration and Continuous Deployment. 

| **Environment**     | **Branch**                              |
|---------------------|-----------------------------------------|
| Production          | deployment/hot-tasking-manager          |
| Production-frontend | deployment/hot-tasking-manager-frontend |
| Staging             | develop                                 |
| TeachOSM            | deployment/teachosm-tasking-manager     |
| Indonesia           | deployment/id-tasking-manager           |

Each environment has its own set of environment variables which are stored as secrets in the CircleCI Organization Settings under Contexts. 

- OPSGENIE_API	
- TM_APP_API_URL
- TM_APP_API_VERSION
- TM_APP_BASE_URL
- TM_CONSUMER_KEY
- TM_CONSUMER_SECRET
- TM_ENABLE_SERVICEWORKER
- TM_MAPBOX_TOKEN
- TM_MATOMO_ENDPOINT
- TM_MATOMO_ID
- TM_ORG_CODE
- TM_ORG_NAME
- TM_ORG_PRIVACY_POLICY_URL
- TM_ORG_URL
- TM_SERVICE_DESK

## Automated Tests

For each Pull Request and branch, the CI runs a set of frontend and backend tests. We have a context in place for setting the database called "tasking-manager-testing", with the following environment variables: 

- POSTGRES_DB	
- POSTGRES_ENDPOINT	
- POSTGRES_USER

Note that the POSTGRES_DB variable should be for the default database (in our case `tm`) the testing script will create a database called `test_$POSTGRES_DB` during setup. 