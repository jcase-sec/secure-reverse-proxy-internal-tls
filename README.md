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

Client Device  
↓  
Internal DNS Resolution  
↓  
Reverse Proxy  
↓  
Backend Service

## Reverse Proxy Overview

![Nginx Proxy Manager Overview](images/NPM-proxy.png)

- Sanitized Nginx Proxy Manager interface demonstrating centralized internal service routing, TLS certificate usage, and reverse proxy management across self-hosted services.

## Security Considerations
- Services are intended for internal-only access
- Backend service ports are not directly exposed externally
- TLS is terminated at the reverse proxy
- Internal certificate trust is managed through a private CA
- VLAN segmentation supports service isolation
- Sensitive values, real hostnames, IP addresses, certificates, and private keys are excluded from this repository

## Lessons Learned
- Reverse proxies simplify access management across multiple internal services
- Internal DNS and TLS improve usability without requiring public exposure
- Certificate trust must be managed carefully across different client devices
- TLS termination centralizes certificate handling but requires secure proxy configuration
- Internal-only services still benefit from encryption, access control, and clean architecture

## Current Focus
- Maintaining clean internal service routing
- Expanding certificate trust across trusted devices
- Improving service organization and documentation
- Reducing unnecessary direct access to backend services

## Repository Notice

This repository is a sanitized documentation project. It intentionally excludes real domains, internal DNS names, IP addresses, credentials, API keys, certificates, private keys, and environment-specific configuration.
