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
