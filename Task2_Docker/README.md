## Introduction

Docker is a **containerization platform** that allows developers to package applications and their dependencies into lightweight, portable units called **containers**.  
Containers ensure that applications run consistently across different environments such as **development**, **testing**, and **production**.

### Why use Docker?
- 🚀 **Portability**: Run anywhere — local machine, cloud, or servers.  
- 🔄 **Consistency**: Same environment across all stages.  
- ⚡ **Speed**: Faster setup compared to virtual machines.  
- 📦 **Efficiency**: Containers share the host OS kernel, making them lightweight.  

---

### Useful Docker Commands

### 🔹 Basic Commands

- **`docker --version`**  
  Displays the installed Docker version.  
  ✅ *Use case*: Verify Docker installation and check its version.  

- **`docker info`**  
  Shows system-wide information about Docker, including containers, images, and system resources.  
  ✅ *Use case*: Check Docker’s current status and configuration.  

- **`docker pull <image>`**  
  Downloads a Docker image from Docker Hub or another registry.  
  ✅ *Use case*: Fetch an image (e.g., `nginx`, `ubuntu`) for local use.  


### 🔹 Container Management

- **`docker run <image>`**  
  Runs a container from a specified image.  
  ✅ *Use case*: Start a new container, e.g., `docker run nginx` to run an Nginx server.  

- **`docker run -d <image>`**  
  Runs a container in detached (background) mode.  
  ✅ *Use case*: Run a service (like a database) without tying up your terminal.  

- **`docker ps`**  
  Lists all running containers.  
  ✅ *Use case*: See which containers are currently active.  

- **`docker ps -a`**  
  Lists all containers (running + stopped).  
  ✅ *Use case*: View stopped containers for debugging or cleanup.  

- **`docker stop <container-id>`**  
  Stops a running container gracefully.  
  ✅ *Use case*: Shut down a test or service when done.  

- **`docker rm <container-id>`**  
  Removes a stopped container.  
  ✅ *Use case*: Clean up unused containers and free resources.  
