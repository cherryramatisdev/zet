# how to run cypress inside a docker container

Reference: https://www.cypress.io/blog/2019/05/02/run-cypress-with-a-single-docker-command/ 

## Run cypress command pointing to internal `http://localhost:3000`

```
docker run -it -v $PWD:/e2e -w /e2e cypress/included:6.2.1 --browser chrome --config baseUrl=http://host.docker.internal:3000
```

## Run cypress command with GUI access (Not tested)

```
DISPLAY=$(ipconfig getifaddr en0):0 docker run -it -v $PWD:/e2e -w /e2e -e DISPLAY cypress/included:6.2.1 open --project . --config baseUrl=http://host.docker.internal:3000
```

## Run cypress inside a github action without installing anything

```
name: included
on: [push]
jobs:
  cypress-run:
    runs-on: ubuntu-latest
    # Docker image with Cypress pre-installed
    # https://github.com/cypress-io/cypress-docker-images/tree/master/included
    container: cypress/included:3.8.3
    steps:
      - uses: actions/checkout@v1
      - run: cypress run
```
