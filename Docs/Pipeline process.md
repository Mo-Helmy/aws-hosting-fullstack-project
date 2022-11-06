## PIPELINE Process

- push the updated code to github dev branch
- merage the code to main
- connect circleCi to github repo
- add environment variables to your circleCi pipeline
  ```
  - AWS_ACCESS_KEY_ID
  - AWS_DEFAULT_REGION
  - AWS_SECRET_ACCESS_KEY
  - POESGRES_HOST     = database-1.cqrlijvzbvhn.us-east-1.rds.amazonaws.com
  - POESGRES_PORT = 5432
  - POESGRES_DB = postgres
  - POSTGRES_USERNAME = postgres
  - POESGRES_PASSWORD = postgres
  - SERVER_PORT = 8080
  - JWT_SECRET = mysecretpassword
  - URL = http://hostingfullstackapp.s3-website-us-east-1.amazonaws.com
  - AWS_REGION = us-east-1
  - AWS_PROFILE = default
  - AWS_BUCKET = arn:aws:s3:::hostingfullstackapp
  ```

From the root of the project:

- API Deploy

  - `npm run api:install`
    - install package.json dependencies
  - `npm run api:deploy`
    - build api server files
    - moving to server folder
    - list all EB enviroments
    - use EB applicalton enviroment
    - set EB environments from circleCi
    - deploy server files

- Frontend Deploy
  - `npm run frontend:install`
    - install package.json dependencies
  - `npm run frontend:deploy`
    - build frontend in production mood
    - upload frontend files to S3 bucket
