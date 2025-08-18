# DevOps Intern Task - Git Commands

This repository is part of my DevOps internship, demonstrating basic Docker Compose commands.

This project uses **Docker Compose** for managing multi-container applications. Below are the most useful commands for development and deployment.

# Useful DockerCompose Commands Guide

---

## 🚀 Quick Start

```bash
# Build and start containers (detached mode)
docker-compose up -d

# View logs (live streaming)
docker-compose logs -f

# Stop containers and remove networks
docker-compose down
```

---

## 📌 Common Commands

### Start services (foreground)
```bash
docker-compose up
```

### Start services in background
```bash
docker-compose up -d
```

### Stop all running services
```bash
docker-compose down
```

### Rebuild containers after changes
```bash
docker-compose up --build
```

### View running services
```bash
docker-compose ps
```

### Check logs of all services
```bash
docker-compose logs
```

### Follow logs (like `tail -f`)
```bash
docker-compose logs -f
```

### Run a command inside a container
```bash
docker-compose exec <service_name> <command>
# Example: docker-compose exec app bash
```

### Stop a specific service
```bash
docker-compose stop <service_name>
```

### Remove stopped containers + networks + volumes
```bash
docker-compose down -v
```

### Restart services
```bash
docker-compose restart
```

### Build or rebuild services without starting
```bash
docker-compose build
```

---

✅ Use these commands as reference while working with Docker Compose in this project.

