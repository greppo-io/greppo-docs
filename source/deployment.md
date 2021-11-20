# Deployment

Greppo is deployed as a web server and can be deployed with Docker. The
greppo-demo repo includes a docker file that can be used to quickly test your
deployments. The following sections details building an image with docker, run
and verify it's working locally, and deploy it to AWS Lightsail.

## Docker Build Steps

First let's build a Docker image and verify that it works locally.

```shell
cd greppo-demo/
docker build -t greppo-ws .  ## build image with the tag `greppo-ws`.
docker images  ## list the images to check if it was built.

## Run docker image locally
docker run --publish 8080:8080 greppo-ws  ## start greppo with the built image,
expose port 8080.
```

At this point you should be able to hit `0.0.0.0:8080` and interact with your
app.

## Lightsail Deployment Steps

```shell
## Setup docker hub
docker login  ## log into Docker Hub.
docker tag greppo-ws stangirala1/greppo-ws  ## point image to a Docker Hub repo
docker push stangirala1/greppo-ws  ## push images to repo
```

With this step the built Docker image should be ready fro deployment from Docker
Hub.


Follow the steps, 
[here](https://aws.amazon.com/blogs/aws/lightsail-containers-an-easy-way-to-run-your-containers-in-the-cloud/),
from the AWS Lightsail documentation to deploy a container.

Make sure to open port `8080` on the Lightsail instance.


