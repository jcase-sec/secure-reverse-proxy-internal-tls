# Secure-Reverse-Proxy-Internal-TLS
Sanitized documentation for an internal reverse proxy and TLS architecture in a segmented homelab environment.

# Secure Reverse Proxy & Internal TLS Architecture

## Overview
Designed and deployed an internal reverse proxy architecture to provide centralized, TLS-secured access to self-hosted services within a segmented homelab environment.

This project focuses on internal service access, TLS termination, DNS-based service routing, certificate trust, and secure documentation practices.

## Technologies Used
- Nginx Proxy Manager
- pfSense
- Pi-hole DNS
- mkcert
- Internal certificate authority
- Docker
- Proxmox
- Linux
- VLAN segmentation

## Project Goals
- Provide friendly internal service names
- Centralize access to self-hosted web services
- Implement HTTPS for internal applications
- Reduce direct access to backend service ports
- Practice internal PKI and certificate trust concepts
- Improve security and usability of homelab services

## Architecture

The environment uses internal DNS records to route service names to a centralized reverse proxy. The reverse proxy terminates TLS and forwards requests to backend services over the internal network.

### Core Components
- Internal DNS records for service name resolution
- Nginx Proxy Manager for reverse proxy management
- mkcert-based internal certificate authority
- Trusted internal certificates deployed to client devices
- Backend services hosted across Proxmox LXCs and Docker containers
- pfSense firewall and VLAN segmentation for network control

### Request Flow
```text
Client Device
    ↓
Internal DNS Resolution
    ↓
Reverse Proxy
    ↓
Backend Service
