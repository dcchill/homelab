# Network

## Core Components

- Router (Asus RT-AX86U Pro)
- Pi-hole (Primary DNS)
- TrueNAS Scale(Application + Storage Host)
- Raspberry Pi Nodes

## Traffic Flow

Internet
↓
Router
↓
Pi-hole (DNS filtering)
↓
TrueNAS Scale(Containers via Nginx Proxy Manager) and Clients