# Images & Containers (VN/EN)

## Hình ảnh (Image)
- Template chỉ đọc để tạo container; build từ Dockerfile.
- Chứa OS base, runtime, libraries, và mã ứng dụng.

## Container
- Instance chạy của image, cô lập môi trường.
- Có thể start/stop/restart/remove.

### Lệnh liên quan
```powershell
# Images
docker pull <image>
docker images
docker rmi <image_id>
docker build -t <tag> .

# Containers
docker run -d -p 8080:80 <image>
docker ps
docker stop <container_id>
docker rm <container_id>
```

---

## Images & Containers (English)

### Image
- Read-only template to create containers; built from a Dockerfile.
- Includes OS base, runtime, libraries, and application code.

### Container
- Running instance of an image; isolated environment.
- Can be started, stopped, restarted, and removed.

#### Related commands
```powershell
# Images
docker pull <image>
docker images
docker rmi <image_id>
docker build -t <tag> .

# Containers
docker run -d -p 8080:80 <image>
docker ps
docker stop <container_id>
docker rm <container_id>
```
