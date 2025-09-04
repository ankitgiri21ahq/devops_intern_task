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
