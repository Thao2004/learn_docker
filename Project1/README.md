# Project 1: Containerize a static website 

## Description:
Build a static website and host it via Docker using Nginx. 

## Purpose:docker
- Learn how to write a basic Dockerfile
- Practice with the instructions: **FROM**, **COPY**, **CMD**, and **EXPOSE**
- Learn these Docker basics:
    - After writing the Dockerfile, build the image:
        `docker build -t <name> .`
    - `.` means “use the current directory as the build context” (look for the Dockerfile and any files to copy).
    - Run the container with port mapping:
        `docker run -d -p <LOCAL_PORT>:<CONTAINER_PORT> <name>`
    - **Run the container with a volumme:**
        - **What is a volume (bind mount in this case)?**
            - A way to link a folder from your host machine into the container.
            - In dev mode, this means changes you make locally show up instantly inside the container.
            - So when you edit files, just refresh the browser, no need to rebuild the image.
            - Command: `docker run -d -p <LOCAL_PORT>:<CONTAINER_PORT> -v ${PWD}:/app <name>`
                - -v → creates the bind mount (host → container).
                - ${PWD} → expands to your current directory on the host (Present Working Directory).
                - /app → the path inside the container where the files will appear.
                - -p → maps the container’s port to your host port.
                - -d → runs in detached mode (background).


### Note: 
- If you **change** your project files or Dockerfile, you **must rebuild the image**.
- You cannot run a new container with the same name if one is already running.
    - Either stop it:
        `docker stop <container_id or name>`
    - Or remove it:
        `docker rm <container_id or name`
- **Multiple Dockerfiles in the same directory**
    - If your project has more than one Dockerfile (for example Dockerfile for production and Dockerfile.live for development), you must tell Docker which one to use.
    - Use the -f flag to specify the file:
        `docker build -f <DockerfileName> -t <image_name> .`