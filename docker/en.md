# Docker - Quick Summary (English)

## What is Docker?
Docker is a containerization platform that packages apps with their dependencies into portable containers that run consistently across environments.

## Core Concepts
- Image: Read-only template used to create containers; built from a Dockerfile
- Container: A running instance of an image; isolated runtime
- Dockerfile: Instructions to build an image (base, deps, commands)
- Registry: Image store (e.g., Docker Hub) to push/pull images

## Basic Commands
```powershell
# Pull an image
docker pull <image>

# Run a container (detached) mapping ports
docker run -d -p 8080:80 <image>

# List containers
docker ps
docker ps -a

# Stop & remove
docker stop <container_id>
docker rm <container_id>

# Build image from Dockerfile in current folder
docker build -t <tag> .

# Logs & shell access
docker logs <container_id>
docker exec -it <container_id> /bin/bash
```

## Simple Dockerfile
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

## Docker Compose
```powershell
# Start services (foreground / detached)
docker-compose up
docker-compose up -d

# Stop and remove services
docker-compose down

# Rebuild and start
docker-compose up --build
```

## Best Practices
- Use small base images (alpine), multi-stage builds
- Pin specific image tags (avoid :latest)
- Don’t run containers as root
- Use volumes for persistent data; keep data out of container layers
- Add .dockerignore to speed builds and reduce image size

Tip: Docker commands are the same on Windows PowerShell, macOS, and Linux.
