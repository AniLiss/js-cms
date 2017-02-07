````
ghost $ docker pull ghost

ghost $ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
ghost                 latest              066a22d980f4        5 days ago          326 MB

ghost $ docker run --name ghost-test -p 8080:2368 -itd ghost
f6a2fb7bd86f542ee1fbf16b258f797c8bc1a78ae323270ccbb5dd9af7f56306

ghost $ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
f6a2fb7bd86f        ghost               "/entrypoint.sh np..."   21 seconds ago      Up 19 seconds       0.0.0.0:8080->2368/tcp   ghost-test

ghost $ docker exec -it ghost-test bash
````

#### After i've created a new post and uploaded file via web-interface i was able to locate it inside the Docker container:
````
root@f6a2fb7bd86f:/usr/src/ghost# find /var/lib/ghost -name 'new_post.png' -type f
/var/lib/ghost/images/2017/02/new_post.png
````