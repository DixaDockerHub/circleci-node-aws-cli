# Description

Dockerfile based on Circle CI Node https://hub.docker.com/r/circleci/node/ supplemented with AWS CLI https://github.com/aws/aws-cli.

The docker images are available at [dockerhub](https://hub.docker.com/r/dixahq/circleci-node-aws-cli)


# Docker image tagging convention

Each push to master in this repository will result in an image being built by dockerhub and tagged with the `latest` tag.

If a release image needs to be done, then an annotated git tag must be created:

```sh
git commit -m "Bump <version-release>" # git commit -m "Bump 10.13.0-1"
git tag -a version-release -m "version-release"  # e.g. git tag -a 10.13.0-1 -m "10.13.0-1"
git push --follow-tags
```

The docker image is tagged with the Node upstream version, appended by the build number, separated by dashes.
In the above example the first build of the Node upstream version `10.13.0`, with includes AWS CLI `1.16.230` is tagged as `10.13.0-1`.
The installed version of the AWS CLI is set explicitly in [Dockerfile](Dockerfile).


# Building Locally

Sometimes you may want to build the image locally in order to test
the installed components. Build locally using [Dockerfile](Dockerfile)

```sh
docker build -t circleci-node-aws-cli .
```

List images

```sh
docker images
```
