# Building the front end service

## 1. Build the container image

To build the container image, you can use docker build. Make sure you are in the root directory of the git repo.

```
$ export DOCKER_USERNAME=your-docker-hub-username
$ docker build -t $DOCKER_USERNAME/workshop-mobile-simulator:1.0 .
```

## 2. Push the container image

In this lab, you can use a Docker Hub to push your container image. Make sure you are also logged in your Docker Hub account when you push the image.

```
$ docker login
$ docker push $DOCKER_USERNAME/workshop-mobile-simulator:1.0
```
