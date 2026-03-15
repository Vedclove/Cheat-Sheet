```{image} https://www.vectorlogo.zone/logos/docker/docker-icon.svg
:height: 60px
:align: left
```

# Docker

```{admonition} Quick Facts
:class: tip
- **Type:** Containerization platform
- **Use cases:** Packaging apps with dependencies, microservices, CI/CD pipelines, local dev environments
- **Key concepts:** Images, Containers, Volumes, Networks, Registries
- **Version:** Docker Engine 26.x (2024)
```

---

:::{dropdown} 📦 Installation
:open:

**Mac OS (Docker Desktop)**
```bash
brew install --cask docker
open -a Docker
```

**Ubuntu/Debian (Docker Engine)**
```bash
sudo apt update
sudo apt install -y docker.io
sudo usermod -aG docker $USER
newgrp docker
```
:::

:::{dropdown} 🚀 Basic Commands

```bash
docker version
docker info
docker pull nginx:latest
docker images
docker ps
docker ps -a
docker run --rm -p 8080:80 nginx:latest
docker exec -it <container> /bin/sh
docker logs -f <container>
docker stop <container>
docker rm <container>
```
:::

:::{dropdown} 📄 Dockerfile

**Minimal app image**
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "app.py"]
```

**Build and run**
```bash
docker build -t myapp:latest .
docker run --rm -p 8000:8000 myapp:latest
```
:::

:::{dropdown} 🐙 Docker Compose

**compose.yaml**
```yaml
services:
  web:
    build: .
    ports:
      - "8000:8000"
    environment:
      - APP_ENV=dev
  db:
    image: postgres:16
    environment:
      - POSTGRES_PASSWORD=example
    ports:
      - "5432:5432"
```

**Commands**
```bash
docker compose up -d
docker compose logs -f
docker compose down
```
:::

:::{dropdown} 💾 Volumes & Networks

**Volumes**
```bash
docker volume ls
docker volume create app-data
docker run -v app-data:/var/lib/app myapp:latest
```

**Networks**
```bash
docker network ls
docker network create app-net
docker run --network app-net --name web myapp:latest
```
:::

:::{dropdown} 🏷️ Common Flags & Options

| Flag | Meaning |
|------|---------|
| `-d` | Detached mode |
| `-p` | Port mapping |
| `-v` | Bind mount or named volume |
| `-e` | Environment variable |
| `--name` | Container name |
| `--rm` | Remove container on exit |
| `-it` | Interactive TTY |
| `--restart` | Restart policy |
:::
