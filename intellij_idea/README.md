# IntelliJ IDEA Dockerized
This is a dockerized version of IntelliJ IDEA with JDK 8. Not that much tested, so there is probably room for improvement. 

To run (on a GNU/Linux system):
```
docker run --name myidea -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -it themkat/idea 
```

The name themkat/idea is simply a name I selected while building. If you build the Dockerfile yourself you can select another name if you want (maybe I will put it on Docker Hub for convencience). 

The option `--name myidea` is simply to create a name for the container. That way you can restart it with the same file system and settings once you are done.

You may want to create a shared volume to use your workspace inside the container.
