# Docker - Các khái niệm cơ bản

## 1. Image (Hình ảnh)
- Template chỉ đọc để tạo container
- Chứa hệ điều hành, runtime, libraries, và mã nguồn ứng dụng
- Được xây dựng từ Dockerfile

## 2. Container
- Instance chạy của image
- Môi trường cô lập để chạy ứng dụng
- Có thể start, stop, restart, delete

## 3. Dockerfile
- File text chứa instructions để build image
- Định nghĩa base image, dependencies, commands

## 4. Docker Registry
- Kho lưu trữ images (ví dụ: Docker Hub)
- Cho phép pull/push images

---

## Core Concepts (English)

### 1. Image
- Read-only template used to create containers
- Includes OS base, runtime, libraries, and app code
- Built from a Dockerfile

### 2. Container
- Running instance of an image
- Isolated environment to run an application
- Can be started, stopped, restarted, removed

### 3. Dockerfile
- Text file with instructions to build an image
- Defines base image, dependencies, and commands

### 4. Docker Registry
- Repository for images (e.g., Docker Hub)
- Supports pull/push of images
