# Fantom Docker

This repo contains files used to generate Fantom base docker images, which can then be used to run
fantom application in a dockerized environment.

You can find built images here: https://hub.docker.com/repository/docker/needleinajaystack/fantom

## Usage

You can use the image in the `FROM` command of a dockerfile for your own Fantom application.
Here's a simple example:

```dockerfile
FROM needleinajaystack/fantom:1.0.77
COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
RUN fan build.fan
CMD ["fan", "MyApp::Main"]
```

## Generate & publish new images

1. Enter the desired subdirectory
2. Build the image: `docker build .`
3. Tag the image: `docker tag <image-id> needleinajaystack/fantom:<version>`
4. Push the image to dockerhub: `docker push needleinajaystack/fantom:<version>`