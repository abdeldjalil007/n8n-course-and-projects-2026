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
- MCP server integration
- Connecting AI agents


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
> **"How to enable virtualization + your laptop model"**

---

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
docker run -d --name n8n -p 5678:5678 -e WEBHOOK_URL=https://subdomain.domain.com -e N8N_DEFAULT_BINARY_DATA_MODE=filesystem -v "C:\Users\%USERNAME%\.n8n:/home/node/.n8n" docker.n8n.io/n8nio/n8n
```
