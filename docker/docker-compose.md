# Docker Compose (VN/EN)

## Tổng quan
Docker Compose giúp định nghĩa và chạy nhiều container Docker bằng một file `docker-compose.yml`.

### Ví dụ `docker-compose.yml`
```yaml
version: '3.8'
services:
	web:
		build: .
		ports:
			- "3000:3000"
		volumes:
			- .:/app
		environment:
			- NODE_ENV=development
	db:
		image: postgres:13
		environment:
			POSTGRES_DB: myapp
			POSTGRES_USER: user
			POSTGRES_PASSWORD: password
		volumes:
			- postgres_data:/var/lib/postgresql/data
volumes:
	postgres_data:
```

### Lệnh thường dùng
```powershell
docker-compose up
docker-compose up -d
docker-compose down
docker-compose up --build
```

### Các option nâng cao

#### Build Services
```yaml
services:
  web:
    build:
      context: .
      dockerfile: Dockerfile.prod
      args:
        BUILD_DATE: 2025-01-01
```

#### Environment Variables (.env file)
```powershell
# .env
POSTGRES_USER=myuser
POSTGRES_PASSWORD=mypass
MYSQL_DATABASE=mydb
```

#### Service Dependencies
```yaml
services:
  web:
    depends_on:
      db:
        condition: service_healthy
  db:
    healthcheck:
      test: ["CMD", "pg_isready"]
      interval: 10s
      timeout: 5s
      retries: 5
```

#### Restart Policy
```yaml
services:
  web:
    restart_policy:
      condition: on-failure
      max_attempts: 3
```

#### Profiles
```yaml
services:
  web:
    profiles: ["production"]
  debug:
    profiles: ["dev"]
```

Chỉ chạy services trong profile `dev`:
```powershell
docker-compose --profile dev up
```

#### Named Volumes vs Bind Mounts
```yaml
# Named volume (quản lý bởi Docker)
volumes:
  db_data:

services:
  db:
    volumes:
      - db_data:/var/lib/postgresql/data

# Bind mount (thư mục cục bộ)
services:
  app:
    volumes:
      - ./src:/app/src
```

#### Multiple Compose Files
```powershell
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up
```

#### Logs & Debugging
```powershell
# View logs
docker-compose logs web

# Follow logs
docker-compose logs -f db

# Exec command in service
docker-compose exec web bash
```

#### Networking
```yaml
# Services trong cùng compose file tự động trong network
# Access bằng service name: http://db:5432
services:
  web:
    depends_on:
      - db
  db:
    ports:
      - "5432:5432"
```

#### Scale Services
```powershell
# Chạy 3 instance của service
docker-compose up -d --scale web=3
```

---

## Overview (English)
Docker Compose defines and runs multi-container Docker applications using a `docker-compose.yml` file.

### Example `docker-compose.yml`
```yaml
version: '3.8'
services:
	web:
		build: .
		ports:
			- "3000:3000"
		volumes:
			- .:/app
		environment:
			- NODE_ENV=development
	db:
		image: postgres:13
		environment:
			POSTGRES_DB: myapp
			POSTGRES_USER: user
			POSTGRES_PASSWORD: password
		volumes:
			- postgres_data:/var/lib/postgresql/data
volumes:
	postgres_data:
```

### Common commands
```powershell
docker-compose up
docker-compose up -d
docker-compose down
docker-compose up --build
```

### Advanced Options

#### Build Services
```yaml
services:
  web:
    build:
      context: .
      dockerfile: Dockerfile.prod
      args:
        BUILD_DATE: 2025-01-01
```

#### Environment Variables (.env file)
```
# .env
POSTGRES_USER=myuser
POSTGRES_PASSWORD=mypass
MYSQL_DATABASE=mydb
```
Reference in docker-compose.yml: `${POSTGRES_USER}`, `${POSTGRES_PASSWORD}`

#### Service Dependencies
```yaml
services:
  web:
    depends_on:
      db:
        condition: service_healthy
  db:
    healthcheck:
      test: ["CMD", "pg_isready"]
      interval: 10s
      timeout: 5s
      retries: 5
```

#### Restart Policy
```yaml
services:
  web:
    restart_policy:
      condition: on-failure
      max_attempts: 3
```

#### Profiles
```yaml
services:
  web:
    profiles: ["production"]
  debug:
    profiles: ["dev"]
```
Run only services in dev profile:
```powershell
docker-compose --profile dev up
```

#### Named Volumes vs Bind Mounts
```yaml
# Named volume (Docker-managed)
volumes:
  db_data:

services:
  db:
    volumes:
      - db_data:/var/lib/postgresql/data

# Bind mount (local directory)
services:
  app:
    volumes:
      - ./src:/app/src
```

#### Multiple Compose Files
```powershell
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up
```

#### Logs & Debugging
```powershell
# View logs
docker-compose logs web

# Follow logs (tail)
docker-compose logs -f db

# Execute command in service
docker-compose exec web bash
```

#### Networking
```yaml
# Services in the same compose file auto-connect to a network
# Access via service name: http://db:5432
services:
  web:
    depends_on:
      - db
  db:
    ports:
      - "5432:5432"
```

#### Scale Services
```powershell
# Run 3 instances of a service
docker-compose up -d --scale web=3
```
