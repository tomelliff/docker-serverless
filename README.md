# Minimal Serverless image

Builds an absolutely minimal image for deploying [Serverless](https://serverless.com/) projects.

The main use is for deploying Serverless projects using [Gitlab CI](https://about.gitlab.com/features/gitlab-ci-cd/).

### Using the image

#### Pulling from [Docker Hub](https://hub.docker.com/r/tomelliff/serverless/)
```sh
docker pull tomelliff/serverless
```

#### Running the image locally
```sh
docker run -it tomelliff/serverless /bin/sh
```
or
```sh
docker run -it tomelliff/serverless serverless info
```

#### Installing npm dependencies in local Docker container
```sh
docker run -it tomelliff/serverless /bin/sh -c "npm install && serverless deploy"
```

#### Using it in Gitlab CI
```yaml
deploy:
  stage: deploy
  image: tomelliff/serverless:latest
  script:
    - serverless deploy
```
