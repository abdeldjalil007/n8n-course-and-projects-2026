# 🤖 Automation & AI agents engineering private course
Welcome to this private course repository.

This repository contains exclusive materials, source code, and resources
designed to support enrolled students throughout the course.

Access is strictly limited to authorized participants.
Please do not share or redistribute any content.

## 📚 Course Overview
This course provides a complete and practical guide to **n8n automation**,
starting from the basics and progressing to advanced real-world workflows.

## 🧩 Course Structure

- Introduction to n8n

- Getting Started  
  - n8n Online (n8n.io)  
  - Self-Hosted n8n (npm, VPS, Docker – Windows, macOS, Linux)

- Updating self-hosted n8n
- From idea to automation planning
- Triggers, actions, and workflow design
- Working with data tables
- Connecting external applications (APIs)
- Building real-world automation workflows
- Connecting AI agent
- MCP server integration



## 🎯 Goal

By the end of this course, students will be able to design, deploy,
and manage professional automation workflows using n8n.

## 📋 Prerequisites

- **n8n installation** We'll cover this in the setup guide
- **Enthusiasm** to learn automation and AI agents!
- **No coding experience is required** - n8n is visual!

## 🖥️ System Preparation (Windows)

### 1. Enable Virtualization (BIOS)

Restart your PC and enter the BIOS settings, then enable:

- **Intel Virtualization Technology (VT-x)** for Intel CPUs  
- **AMD-V** for AMD CPUs  

Save the changes and exit the BIOS to apply them.

> ℹ️ If you cannot find this option, search on YouTube:  
> **"How to enable virtualization + your laptop (OR PC) model"**


### 2. Install WSL (Windows Subsystem for Linux)

Open **Command Prompt as Administrator** and run:

```bash
wsl --install
```
Restart your PC when asked.

### 3. Download Docker Desktop

Download and install [**Docker Desktop**](https://www.docker.com/products/docker-desktop/) from the official website.
>
To know which version is compatible with your PC :
1. Press <kbd>Windows</kbd> + <kbd>R</kbd>
2. Type `cmd` and press Enter to open Command Prompt  
3. In the Command Prompt window, type the following command and press Enter:
```cmd
   echo %PROCESSOR_ARCHITECTURE%
```
| If the output is... | You should choose... |
| :--- | :--- |
| **AMD64** | **Download for Windows – AMD64** |
| **ARM64** | **Download for Windows – ARM64** |
>
### 4. Download the n8n Docker Image
Make sure Docker Desktop is running, open CMD then pull the n8n image using :
```cmd
   docker pull docker.n8n.io/n8nio/n8n
```

### 5. Run n8n in Docker

Now you can start n8n using : 

```cmd
docker run -d --name n8n -p 5678:5678 -e N8N_DEFAULT_BINARY_DATA_MODE=filesystem -v "C:\Users\%USERNAME%\.n8n:/home/node/.n8n" docker.n8n.io/n8nio/n8n
```

```cmd
docker run -d --name n8n -p 5678:5678 -e WEBHOOK_URL=https://subdomain.domain.com -e N8N_DEFAULT_BINARY_DATA_MODE=filesystem -v "C:\Users\%USERNAME%\.n8n:/home/node/.n8n" docker.n8n.io/n8nio/n8n
```
### 6. Tunnel configuration

Follow the course.

Links  needed :

- **Domain discount finder:** [TLD-List](https://tld-list.com)
- **Cloudflare**: [Link](https://dash.cloudflare.com)

> **ℹ️ If you cannot buy a domain, you can ask for a ready one from us (Registered members only)**

## 🖥️ System Preparation (Linux – Ubuntu/Debian)

### 1. Update Your System
Open a terminal and run:

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Docker Engine

Run the following commands **one by one, in this exact order:**


```bash
  sudo apt install ca-certificates curl gnupg -y
```


```bash
  sudo install -m 0755 -d /etc/apt/keyrings
```

```bash
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

```bash
  sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

```bash
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo $VERSION_CODENAME) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
  sudo apt update
```

```bash
  sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

### 3. Allow Docker to Run Without sudo

Add your user to the Docker group:
```bash
  sudo usermod -aG docker $USER
```
Apply the group changes:
```bash
  newgrp docker
```

### 4. Download the n8n Docker Image

Pull the official n8n image:
```bash
  docker pull docker.n8n.io/n8nio/n8n
```
### 5. Run n8n in Docker
```bash
docker run -d \
  --name n8n \
  -p 5678:5678 \
  -e WEBHOOK_URL=https://subdomain.domain.com \
  -e N8N_DEFAULT_BINARY_DATA_MODE=filesystem \
  -v ~/.n8n:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```

### 6. Tunnel configuration

Follow the course.

Links  needed :

- **Domain discount finder:** [TLD-List](https://tld-list.com)
- **Cloudflare**: [Link](https://dash.cloudflare.com)

> **ℹ️ If you cannot buy a domain, you can ask for a ready one from us (Registered members only)**



## Getting started (Self-hosted)
After completing the installation and starting the n8n container, the service
will be running locally on your machine.

To access the n8n interface, open your web browser and navigate to:

http://localhost:5678

Once the page loads, you will see the n8n welcome screen, where you create an account, and then you can begin
creating workflows, configuring credentials, and exploring available nodes.

---
---
## Updating n8n Docker Container

To ensure your n8n instance remains secure and benefits from the latest
features and improvements, follow the steps below to update the Docker
container.

| Step | Command | Description |
|------|---------|-------------|
| **1. Stop Container** | <pre><code>docker stop n8n</code></pre> | Stop the running n8n container |
| **2. Remove Container** | <pre><code>docker rm n8n</code></pre> | Remove the old container (data remains in volume) |
| **3. Pull Latest Image** | <pre><code>docker pull docker.n8n.io/n8nio/n8n</code></pre> | Download the latest n8n Docker image |
| **4. Start New Container** | For this, go back to **Run n8n in Docker** section to copy the code from the installation guide [For Windows](https://github.com/abdeldjalil007/n8n-course-and-projects-2026?tab=readme-ov-file#5-run-n8n-in-docker) or [For Linux](https://github.com/abdeldjalil007/n8n-course-and-projects-2026?tab=readme-ov-file#5-run-n8n-in-docker-1) | Launch updated n8n with preserved data and settings |


## n8n Projects 

### 🟢 **Beginner Level Projects**

| Project | Description | Source File | 
|---------|-------------|-------------|
| **Project name** | Description | [📁 Download](workflows/file.json) | 
| **Project name** | Description | [📁 Download](link) | 

### 🟡 **Intermediate Level Projects**

| Project | Description | Source File | 
|---------|-------------|-------------|
| **Project name** | Description | [📁 Download](link) | 
| **Project name** | Description | [📁 Download](link) | 

### 🔴 **Advanced Level Projects**

| Project | Description | Source File | 
|---------|-------------|-------------|
| **Project name** | Description | [📁 Download](link) | 
| **Project name** | Description | [📁 Download](link) | 


