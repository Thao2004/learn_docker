# Build a first Dockerfile

# 1. Start with a base image
FROM nginx:alpine

# 2. Copy project files from the local machine into the container's web root
# Read https://hub.docker.com/_/nginx to understand why choose that path
COPY . /usr/share/nginx/html

# 3. Document that the container listens on port 80
EXPOSE 80

