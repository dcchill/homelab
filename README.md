# Darian's Homelab Infrastructure

## Overview

This repository documents my self-hosted homelab built for:

- Media automation
- Network services
- Storage and backups
- Monitoring
- Game hosting
- Smart home integration
- Ad blocking

This is centered around TrueNAS Scale with additional Raspberry Pi nodes.

--------------------------------------------------------------------------------

# Core Infrastructure

## TrueNAS Server

Primary storage and container host.
- AMD Ryzen 5 5600X
- 64gb DDR4 Memory
- 2 x 12tb in Raid 1
- Dell NVIDIA Quadro P600 (for media transcoding)

### Responsibilities
- Application hosting
- Media storage
- ISO Storage
- Backup storage
- SMB/NFS shares

--------------------------------------------------------------------------------

# Applications (TrueNAS)

## Media Stack

- Sonarr > Searching for new shows
- Radarr > Searching for new movies
- Prowlarr 
- Jellyfin > Hosts shows and movies to friends and family
- CleanUpArr
- Immich > Cloud-like personal photo and video storage backups
  
### Supporting
- Nginx Proxy Manager
- Portainer
- OpenSpeedTest

--------------------------------------------------------------------------------

# Game Servers

- Crafty Controller (Minecraft management)
- Terraria Server

Backups stored in:
`/McBackups`

--------------------------------------------------------------------------------

# Storage Layout

### Primary Shares

- `/Media`
- `/Videos`
- `/Photos`
- `/Uploads`
- `/Minecraft`
- `/Terraria`
- `/Games`
- `/3DPrints`

ZFS snapshots enabled for critical datasets.

--------------------------------------------------------------------------------

# Raspberry Pi Infrastructure

## Pi #1 – qBittorrent Node
- Dedicated torrent client
- Isolated from TrueNAS
- Mounted media path
- MulVAD VPN

## Pi #2 – Home Assistant
- Smart home automation
  
## Pi #3 – Pi-hole
- Network-wide DNS filtering
- Ad blocking
- Custom DNS entries

--------------------------------------------------------------------------------

# Networking

- Reverse proxy for internal services
- Internal DNS via Pi-hole
- Segmented application deployment
- Port forwarding minimized
- WireGuard VPN built into router.

## Domain Management

- Domain managed through Cloudflare
- A records pointing to public WAN IP
- CNAME records for service subdomains
- SRV records configured for Minecraft servers
- Reverse Proxy
- Nginx Proxy Manager running on TrueNAS
- Subdomain-based routing
- Automatic Let's Encrypt SSL certificates
- Public services proxied internally
--------------------------------------------------------------------------------

# Backup Strategy

- ZFS snapshots
- Minecraft scheduled backups
- Important files mirrored
- Off-device storage for critical data

--------------------------------------------------------------------------------

# Technologies Used

- TrueNAS
- ZFS
- Docker / Portainer
- Raspberry Pi OS
- Nginx Proxy Manager
- Linux CLI administration

--------------------------------------------------------------------------------
