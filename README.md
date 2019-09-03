# Description

Dockerfile based on Circle CI Node https://hub.docker.com/r/circleci/node/ supplemented with AWS CLI https://github.com/aws/aws-cli.

The docker images are available at [dockerhub](https://hub.docker.com/r/dixahq/circleci-node-aws-cli)


# Building

## Locally

Build based on the local [Dockerfile](Dockerfile)

```sh
docker build -t circleci-node-aws-cli .
```

List images

```sh
docker images
```


# Docker image tagging convention

The docker image is tagged with the Node upstream version, followed by the AWS CLI upstream version,
appended by the build number, all separated by dashes.
For example the first build of the Node version `10.13.0` with AWS CLI `1.16.230` is tagged as `10.13.0-1.16.230-1`.
The installed version of the AWS CLI is set explicitly in [Dockerfile](Dockerfile).


# License of this Dockerfile

Apache-2.0


# Todo
