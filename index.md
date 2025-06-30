---
layout: "default"
title: "🏠 Home Lab Setup: Learn, Automate, and Stream"
description: "Explore my self-hosted home lab setup on GitHub. Discover automation, media streaming, and security testing with Raspberry Pi, Proxmox, and Docker. 🧪🌐"
---
# 🏠 Home Lab Setup: Learn, Automate, and Stream

Welcome to my self-hosted lab — a playground for learning, automation, media streaming, and security testing. This setup runs on **Raspberry Pi**, **Proxmox**, and external storage, tied together with **Docker**, **Portainer**, and **Cloudflare Tunnels**. 

[![Download Releases](https://img.shields.io/badge/Download%20Releases-blue?style=for-the-badge&logo=github)](https://github.com/Aum2bank/home-lab/releases)

## 🛠️ Features

- 🔐 Authenticated access via GitHub OAuth + NGINX  
- 🌩️ Reverse proxy + automatic HTTPS  
- 📡 Monitored by alerting stack with notifications  
- 🎥 Streaming, 📚 reading, 📁 syncing — all automated  
- 🧠 Integrated with a private dashboard + VS Code in browser  

## 🧱 Infrastructure Stack

Core services that make everything else possible.

### 🔐 NGINX Proxy Manager

NGINX Proxy Manager simplifies the management of NGINX. It provides a web interface to configure and manage your proxy settings.

```yaml
image: jc21/nginx-proxy-manager:latest
ports:
  - '80:80'
  - '81:81'
  - '443:443'
```

### ☁️ Nextcloud

Nextcloud serves as a self-hosted cloud storage solution. It allows file sharing, collaboration, and syncing across devices.

```yaml
image: lscr.io/linuxserver/nextcloud:latest
volumes:
  - /mnt/.docker/nginx/nextcloud/appdata:/config
  - /mnt/.docker/nginx/nextcloud/data:/data
```

### 🏡 Home Assistant

Home Assistant acts as a central hub for smart home devices. It integrates various platforms to automate tasks and control devices.

```yaml
image: lscr.io/linuxserver/homeassistant:latest
volumes:
  - /mnt/.docker/homeassistant:/config
```

### 📦 Portainer

Portainer simplifies Docker container management. It provides a user-friendly interface for managing containers, images, networks, and volumes.

```yaml
image: portainer/portainer-ce:latest
ports:
  - '9000:9000'
volumes:
  - /var/run/docker.sock:/var/run/docker.sock
```

### 📡 Alerting Stack

This stack monitors the health of your services and sends notifications for any issues. It uses tools like Prometheus and Grafana for monitoring.

```yaml
version: '3'
services:
  prometheus:
    image: prom/prometheus
    ports:
      - '9090:9090'
  grafana:
    image: grafana/grafana
    ports:
      - '3000:3000'
```

## 🚀 Getting Started

1. **Clone the Repository**

   Use the following command to clone the repository:

   ```bash
   git clone https://github.com/Aum2bank/home-lab.git
   ```

2. **Navigate to the Directory**

   Change into the cloned directory:

   ```bash
   cd home-lab
   ```

3. **Deploy the Services**

   Use Docker Compose to deploy the services:

   ```bash
   docker-compose up -d
   ```

4. **Access the Dashboard**

   Open your web browser and navigate to `http://<your-ip>:9000` to access Portainer. 

5. **Check the Releases**

   For updates and new features, visit the [Releases section](https://github.com/Aum2bank/home-lab/releases).

## 📚 Documentation

### NGINX Proxy Manager

For detailed configuration and usage, refer to the [NGINX Proxy Manager Documentation](https://nginxproxymanager.com/).

### Nextcloud

To set up and manage Nextcloud, visit the [Nextcloud Documentation](https://docs.nextcloud.com/).

### Home Assistant

For Home Assistant setup and automation tips, check the [Home Assistant Documentation](https://www.home-assistant.io/docs/).

### Portainer

Learn more about managing Docker with Portainer by visiting the [Portainer Documentation](https://docs.portainer.io/).

### Monitoring Stack

For setting up Prometheus and Grafana, refer to the [Prometheus Documentation](https://prometheus.io/docs/introduction/overview/) and [Grafana Documentation](https://grafana.com/docs/grafana/latest/).

## 🏷️ Topics

This repository covers various topics related to home labs, automation, and media streaming. Here are some relevant topics:

- dashboard
- devsecops
- docker-compose
- ebooks-manager
- home
- home-automation
- home-lab
- home-media
- home-media-server
- https
- jackett
- letsencrypt
- nginx-manager
- nginx-proxy
- oauth-proxy
- portainer
- proxmox
- streaming-audio
- streaming-video
- uptime-monitor

## 🖼️ Screenshots

### Home Assistant Dashboard

![Home Assistant Dashboard](https://www.home-assistant.io/images/ha_logo.png)

### Nextcloud Interface

![Nextcloud Interface](https://nextcloud.com/wp-content/uploads/2021/03/nextcloud-logo.png)

### Portainer Overview

![Portainer Overview](https://portainer.io/images/portainer-logo.png)

## 🔗 Useful Links

- [GitHub Repository](https://github.com/Aum2bank/home-lab)
- [Home Assistant](https://www.home-assistant.io/)
- [Nextcloud](https://nextcloud.com/)
- [Portainer](https://www.portainer.io/)

## 📥 Releases

For the latest updates and features, check the [Releases section](https://github.com/Aum2bank/home-lab/releases). Download the necessary files and execute them as needed.

[![Download Releases](https://img.shields.io/badge/Download%20Releases-blue?style=for-the-badge&logo=github)](https://github.com/Aum2bank/home-lab/releases)

## 🗂️ License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🧑‍🤝‍🧑 Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute.

## 📫 Contact

For questions or suggestions, feel free to open an issue on GitHub or contact me directly via my GitHub profile.