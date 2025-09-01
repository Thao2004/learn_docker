# Project 1: Containerize a static website 

## Description:
Build a static website and host it via Docker using Nginx. 

## Purpose:
- Learn how to write a basic Dockerfile
- Practice with the instructions: **FROM**, **COPY**, and **EXPOSE**
- Learn these Docker basics:
    - After writing the Dockerfile, build the image:
        `docker build -t <name> .`
    - `.` means “use the current directory as the build context” (look for the Dockerfile and any files to copy).
    - Run the container with port mapping:
        `docker run -d -p <LOCAL_PORT>:<CONTAINER_PORT> <name>`


### Note: 
- If you **change** your project files or Dockerfile, you **must rebuild the image**.
- You cannot run a new container with the same name if one is already running.
    - Either stop it:
        `docker stop <container_id or name>`
    - Or remove it:
        `docker rm <container_id or name`