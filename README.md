# Homelab
Self-hosted homelab built on Ubuntu 24.04 running Docker and 
various self-hosted services. Started this project to develop 
practical IT infrastructure skills and get hands on experience 
with containerisation and Linux ahead of starting an IT apprenticeship.
## Hardware
-CPU: AMD Ryzen 7 7800 X3D
-RAM: 32GB
-GPU: AMD 9070XT 16GB
-Storage: 1TB dedicated SSD (Ubuntu), 2TB (Windows)
-Network: Ethernet
## Operating System
- Ubuntu 24.04.4 LTS (dual boot alongside Windows)
- Dedicated 1TB NVMe SSD
- Docker Engine + Docker Compose installed

## What I'm running

- **Portainer** - Web UI for managing my Docker containers
- **Uptime Kuma** - Monitors whether my services are up or down
- **Jellyfin** - Self hosted media server
- **Pi-hole** - DNS ad blocker, currently moving this to a 
  dedicated Raspberry Pi 4 as it caused networking conflicts 
  on my main machine

## Challenges and lessons learned

- Ran into port 53 conflicts when deploying Pi-hole on my main 
  machine because Ubuntu's systemd-resolved was already using it. 
  Learned about how services claim ports and why dedicated hardware 
  matters for network services.

- Discovered that localhost behaves differently inside a Docker 
  container — it refers to the container itself, not the host machine. 
  Had to use my actual network IP instead.

- Pi-hole version 6 changed how passwords are set, which meant 
  following older tutorials didn't work. Had to troubleshoot and 
  find the new command myself.

- Learned the difference between named volumes and bind mounts 
  the practical way — Jellyfin needed both.

## What's next
- Move Pi-hole to a dedicated Raspberry Pi 4 
- Set up Nginx Proxy Manager for HTTPS across all services
- Add Nextcloud for self-hosted file storage
- get a better understanding of Proxmox for proper VM management to integrate into my homelab
