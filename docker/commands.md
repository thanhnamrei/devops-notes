# Docker - Lệnh cơ bản

## Quản lý Images
```bash
# Tải image từ registry
docker pull <image_name>

# Liệt kê images
docker images

# Xóa image
docker rmi <image_id>

# Build image từ Dockerfile
docker build -t <tag_name> .
```

## Quản lý Containers
```bash
# Chạy container từ image
docker run -it <image_name>

# Chạy container ở background
docker run -d <image_name>

# Liệt kê containers đang chạy
docker ps

# Liệt kê tất cả containers
docker ps -a

# Dừng container
docker stop <container_id>

# Khởi động lại container
docker restart <container_id>

# Xóa container
docker rm <container_id>
```

## Các options quan trọng
```bash
# Mount volume
docker run -v /host/path:/container/path <image>

# Expose port
docker run -p 8080:80 <image>

# Set environment variables
docker run -e ENV_VAR=value <image>

# Interactive mode
docker run -it <image> /bin/bash
```

---

## Basic Commands (English)

### Image Management
```powershell
# Pull image from registry
docker pull <image_name>

# List images
docker images

# Remove image
docker rmi <image_id>

# Build image from Dockerfile
docker build -t <tag_name> .
```

### Container Management
```powershell
# Run a container from image
docker run -it <image_name>

# Run in background (detached)
docker run -d <image_name>

# List running containers
docker ps

# List all containers
docker ps -a

# Stop a container
docker stop <container_id>

# Restart a container
docker restart <container_id>

# Remove a container
docker rm <container_id>
```

### Common Options
```powershell
# Mount a host path as a volume
docker run -v C:/host/path:/container/path <image>

# Map ports (host:container)
docker run -p 8080:80 <image>

# Set environment variables
docker run -e ENV_VAR=value <image>

# Interactive shell
docker run -it <image> /bin/bash
```
