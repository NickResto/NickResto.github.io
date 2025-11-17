---
layout: page
title: HomeLab
description: A self-hosted lab for virtualization, storage, automation, and experimentation.
img: assets/img/homelab.png
importance: 1
category: personal
related_publications: false
---

Welcome to my HomeLab. This environment is designed for learning, self-hosting, and exploring virtualization, containers, networking, and storage. 
Below is an overview of the hardware and services powering the lab.

---

## Server: Lenovo ThinkCentre M90q
**Specs**
- Intel Core i5-10600 @ 3.30 GHz
- 32 GB DDR4 RAM (upgraded from 16 GB)
- Storage: 1 TB SSD + 256 GB SSD
- ASRock A380 Challenger ITX 6GB OC GPU (passed through for transcoding)

**Operating System**
- Proxmox VE Hypervisor

**Nodes**
- **Media Container (Ubuntu)**
  - Mounted ZFS storage
  - Acts as separate data layer for media stack
- **Media Server VM (Ubuntu Server)**
  - Jellyfin with GPU passthrough for hardware transcoding
  - Apps Dockerized
  - Data mounted from media container
  - Tailscale for remote access
  - Credit to TechHutTV (https://github.com/TechHutTV/homelab.git)
- **Web App VM (Ubuntu Server)**
  - Hosting class project site
  - Docker containers
  - Cloudflare Tunnel exposing frontend

---

## NAS: ZimaBoard 832
**Specs**
- Intel Celeron N3450 @ 1.1 GHz
- 8 GB RAM
- 32 GB eMMC
- Drives:
  - 2× 4 TB WD Blue HDDs (mirrored ZFS pool)
  - 256 GB SSD (Pi-hole + future apps)

**Operating System**
- TrueNas

**Uses**
- NFS shares to Proxmox
- Pi-hole running on SSD

---

## Additional Hardware
- APC UPS
- GeeekPi T1 10" 8U Server Cabinet
- TP-Link 5-Port Unmanaged Switch
- eero Pro 6E Mesh WiFi Router

---
<!---
## Gallery

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/homelab1.jpg" title="Server + NAS" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/homelab2.jpg" title="Rack" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/homelab3.jpg" title="Proxmox Environment" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
Hardware, rack, and virtualization dashboard.
</div>

---
-->
