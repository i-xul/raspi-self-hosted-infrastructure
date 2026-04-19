Architecture
Overview

This document describes the structure of the self-hosted Raspberry Pi infrastructure.

The system is built around multiple devices, each responsible for a specific role. The goal is to keep services organized, maintainable, and easy to troubleshoot.

High-Level Architecture
                ┌─────────────────────────────┐
                │         Internet            │
                └─────────────┬───────────────┘
                              │
                      ┌───────▼────────┐
                      │   Router       │
                      └───────┬────────┘
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
┌───────▼────────┐   ┌────────▼────────┐   ┌────────▼────────┐
│ Raspberry Pi 5 │   │ Raspberry Pi 4  │   │ Raspberry Pi 4  │
│ (Main Server)  │   │ (DNS/Display)   │   │ (Energy System) │
└───────┬────────┘   └────────┬────────┘   └────────┬────────┘
        │                     │                     │
        │                     │                     │
  ┌─────▼──────────────┐      │              ┌──────▼─────────────┐
  │ Application Layer  │      │              │ Energy Monitoring  │
  │                    │      │              │ (Victron / MPPT)   │
  │ - Immich           │      │              └────────────────────┘
  │ - Navidrome        │      │
  │ - Kavita           │      │
  │ - Nextcloud        │      │
  │ - Dashboard        │      │
  │ - Flask tools      │      │
  └─────┬──────────────┘      │
        │                     │
  ┌─────▼──────────────┐      │
  │ Infrastructure     │      │
  │                    │      │
  │ - Nginx            │      │
  │ - Fail2ban         │      │
  │ - Backup           │      │
  │ - Audit            │      │
  │ - Updates          │      │
  │ - Notifications    │      │
  └────────────────────┘      │
                              │
                       ┌──────▼─────────────┐
                       │ Network Services   │
                       │                   │
                       │ - Pi-hole         │
                       │ - MagicMirror     │
                       └───────────────────┘
Node Responsibilities
Raspberry Pi 5 (Main Server)

Acts as the primary service host.

Responsibilities:

runs application-level services (media, cloud, dashboard)
handles reverse proxy via Nginx
enforces security controls (Fail2ban)
executes automation workflows (backup, audit, updates)
serves internal tools (Flask applications)
Raspberry Pi 4 (DNS / Display)

Handles network-level services and local display.

Responsibilities:

DNS filtering via Pi-hole
dashboard display via MagicMirror
provides visibility into system status
Raspberry Pi 4 (Energy System)

Dedicated to energy monitoring.

Responsibilities:

runs Venus OS (Victron)
connected to MPPT controller
provides real-time energy data and system status
Service Flow

Typical request flow:

user connects to a service through the network
request is routed via router to Raspberry Pi 5
Nginx receives the request
request is forwarded to the appropriate service:
Flask app (via uWSGI)
media service (Immich, Navidrome, etc.)
Nextcloud or other services
response is returned through Nginx to the user
Operational Flow

System maintenance and monitoring follow a continuous loop:

backups run on a schedule
system updates are automated
security audits run periodically
Fail2ban monitors logs and blocks suspicious activity
Telegram notifications provide real-time alerts

This creates a feedback loop:

Monitor → Detect → Notify → Adjust → Repeat
Design Considerations

Key design choices include:

separation of responsibilities across devices
minimizing single points of failure where possible
using lightweight tools suitable for Raspberry Pi hardware
prioritizing maintainability over complexity
building observability through logging and reporting
Summary

The infrastructure is designed as a practical, evolving system rather than a fixed configuration.

It balances:

functionality (multiple services)
security (layered protection)
automation (reduced manual work)
visibility (audit and monitoring)

This structure allows the system to grow while remaining manageable.
