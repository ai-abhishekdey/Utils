## Docker Commands

**Author: Abhishek Dey**

**Last modified: 28/01/2023**


### steps to push a custom built docker image from local machine to gcr


* docker [tag](https://docs.docker.com/engine/reference/commandline/tag/)

```

docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]


eg: docker tag demo_docker_image:latest gcr.io/<project_path>/demo_docker_image:latest

```

* docker [push](https://docs.docker.com/engine/reference/commandline/push/)

```

docker push TARGET_IMAGE[:TAG]


eg: docker push gcr.io/vision-intel-89531/track-confidence:latest

```

### steps to pull a docker image from gcr to local machine


* docker [pull](https://docs.docker.com/engine/reference/commandline/pull/)

```

docker pull TARGET_IMAGE[:TAG]


eg: docker pull gcr.io/vision-intel-89531/track-confidence:latest

```

### Command to install the additional packages inside the docker container and update the container with the updated packages 



