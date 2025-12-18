# Best Practices

## 1. Image Optimization
- Sử dụng multi-stage builds
- Chọn base image nhỏ (alpine)
- Giảm số lượng layers khi hợp lý
- Sử dụng `.dockerignore` để loại trừ file không cần thiết

## 2. Security
- Không chạy container với root user
- Scan images để phát hiện vulnerabilities
- Sử dụng image tags cụ thể (tránh dùng `:latest`)

## 3. Data Management
- Sử dụng volumes cho persistent data
- Tách data khỏi logic của container

---

## Best Practices (English)

### 1. Image Optimization
- Use multi-stage builds
- Prefer small base images (alpine)
- Reduce unnecessary layers
- Add `.dockerignore` to exclude non-essential files

### 2. Security
- Avoid running as root in containers
- Scan images for vulnerabilities
- Pin image tags (avoid `:latest`)

### 3. Data Management
- Use volumes for persistent data
- Keep data separate from container logic
