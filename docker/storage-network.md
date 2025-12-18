# Volumes và Networks

## Volumes
```bash
# Tạo volume
docker volume create my-vol

# Liệt kê volumes
docker volume ls

# Mount volume
docker run -v my-vol:/data <image>
```

## Networks
```bash
# Tạo network
docker network create my-network

# Kết nối container vào network
docker run --network my-network <image>
```

---

## Volumes (English)
```powershell
# Create a volume
docker volume create my-vol

# List volumes
docker volume ls

# Mount a named volume
docker run -v my-vol:/data <image>
```

## Networks (English)
```powershell
# Create a network
docker network create my-network

# Attach container to network
docker run --network my-network <image>
```
