# Hosting a Full-Stack Application

### Dependencies

```
- Node v14.15.1 (LTS) or more recent. While older versions can work it is advisable to keep node to latest LTS version

- npm 6.14.8 (LTS) or more recent, Yarn can work but was not tested for this project

- AWS CLI v2, v1 can work but was not tested for this project

- AWS EB CLI

- A RDS database running Postgres.

- A S3 bucket for hosting uploaded pictures.

```

### AWS setup

- RDS - database host: database-3.c1r9noshx1gc.us-east-1.rds.amazonaws.com
- RDS - database port: 5432
- RDS - database name: postgres

- Elastic Beanstalk - backend: http://hostingfullstackapp1-env.eba-yr6jemcs.us-east-1.elasticbeanstalk.com/

- S3 Bucket - frontend: http://hosting-fullstack-app-1.s3-website-us-east-1.amazonaws.com/index.html

### Enviroment variables for Elastic Beanstalk api

```
- POESGRES_HOST     = database-3.c1r9noshx1gc.us-east-1.rds.amazonaws.com
- POESGRES_PORT     = 5432
- POESGRES_DB       = postgres
- POSTGRES_USERNAME = postgres
- POESGRES_PASSWORD = postgres
- SERVER_PORT       = 8080
- JWT_SECRET        = mysecretpassword
- URL               = http://hosting-fullstack-app-1.s3-website-us-east-1.amazonaws.com/index.html
- AWS_REGION        = us-east-1
- AWS_PROFILE       = default
- AWS_BUCKET        = arn:aws:s3:::hosting-fullstack-app-1

```

## CI/CD PIPELINE

- connect circleCi to github repo
- add environment variables to your project
  ```
  - AWS_ACCESS_KEY_ID
  - AWS_DEFAULT_REGION
  - AWS_SECRET_ACCESS_KEY
  ```

From the root of the project:

- API Deploy

  - `npm run api:install`
    - install package.json dependencies
  - `npm run api:deploy`
    - build api server
    - moving to server folder
    - list all EB enviroments
    - use EB applicalton enviroment
    - deploy server files

- Frontend Deploy
  - `npm run frontend:install`
    - install package.json dependencies
  - `npm run frontend:deploy`
    - build frontend in production mood
    - upload frontend files to S3 bucket

## Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1. `cd starter/udagram-frontend`
1. `npm run test`
1. `npm run e2e`

There are no Unit test on the back-end

### Unit Tests:

Unit tests are using the Jasmine Framework.

### End to End Tests:

The e2e tests are using Protractor and Jasmine.

## Built With

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework

## License

[License](LICENSE.txt)
