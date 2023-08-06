# simple-jenkins-pipeline

- Based on [this](https://www.jenkins.io/doc/tutorials/build-a-python-app-with-pyinstaller/)

## Running

- `docker-compose up`
- use the password given in jenkins-blueocean logs

## Accessing docker container

- `docker exec -it jenkins-blueocean bash`

## Accessing the Docker logs

- when we need to access the Jenkins console logs

## BUG:

- it seems the dns name isn't being registred with the certs so when accessing the jenkins container we will need to do some manual process
- `docker ps` to get the error message like this
  - `error during connect: Get "https://jenkins-docker:2376/v1.24/containers/json": tls: failed to verify certificate: x509: certificate is valid for a88fb2d0600f, docker, localhost, not jenkins-docker`
- set the environment variable, `DOCKER_HOST=tcp://a88fb2d0600f:2376`
- now `docker ps` works
