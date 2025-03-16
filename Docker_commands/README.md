## Docker Commands

**Author: Abhishek Dey**

**Last modified: 28/01/2023**


### List Docker images:

```
docker images

```


### List Docker containers:

```
docker ps

```


### Steps to push a custom built docker image from local machine to gcr:


* docker [tag](https://docs.docker.com/engine/reference/commandline/tag/)

```

docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]


eg: docker tag demo_docker_image:latest gcr.io/<project_path>/demo_docker_image:latest

```

* docker [push](https://docs.docker.com/engine/reference/commandline/push/)

```

docker push TARGET_IMAGE[:TAG]


eg: docker push gcr.io/<project_path>/demo_docker_image:latest

```

### Steps to pull a docker image from gcr to local machine:


* docker [pull](https://docs.docker.com/engine/reference/commandline/pull/)

```

docker pull TARGET_IMAGE[:TAG]


eg: docker pull gcr.io/<project_path>/demo_docker_image:latest

```

### Command to commit a container’s file changes or settings into a new image:


* docker [commit](https://docs.docker.com/engine/reference/commandline/commit/)

```

docker commit CONTAINER_ID TARGET_IMAGE[:TAG]

eg: docker commit c3f279d17e0a  demo_docker_image:latest


```

### Command to Delete docker image by image_id:

```

docker rmi -f <image_id>

```

### Command to Stop Docker container by container_id:


```

docker stop <container_id>

```

## Useful links:

* [Nvidia-Pytorch Docker images](https://docs.nvidia.com/deeplearning/frameworks/pytorch-release-notes/running.html)

* [Nvidia-Tensorflow Docker images](https://docs.nvidia.com/deeplearning/frameworks/tensorflow-release-notes/rel-22-10.html#rel-22-10)
