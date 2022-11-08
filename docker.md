```
# docker run <image> -> creates a new container every time
# docker start <container_id/name> 
# docker stop <container_id/name>

# docker run --detach --name web nginx:latest
# docker run -it --link web:web --name web_test busybox:latest /bin/sh    (-it)
# docker create <image> -> only creates container, does not start it

# docker rename webid webid-old

# docker logs web
# docker exec <docker_ip/name> <command> -> executes a command

# docker ps -a

# docker inspect --format "{{.State.Running}}" wp

# docker rm web
```
