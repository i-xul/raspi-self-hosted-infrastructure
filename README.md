# raspi-self-hosted-infrastructure

Self-hosted Raspberry Pi infrastructure with media, cloud, DNS, dashboard, and automation components.

## Overview

This repository documents a self-hosted infrastructure built on multiple Raspberry Pi devices.

The environment includes media services, cloud storage, DNS filtering, dashboards, automation, and security controls. The goal is to maintain a practical, reliable, and secure home server setup while continuously improving system administration skills.

## Architecture

The infrastructure is distributed across multiple Raspberry Pi devices:

* **Raspberry Pi 5**

  * primary application and service host
* **Raspberry Pi 4 (1)**

  * DNS filtering and display services
* **Raspberry Pi 4 (2)**

  * dedicated energy monitoring system (Victron / Venus OS)

## Core Services

### Raspberry Pi 5

* **Immich** – self-hosted photo and media management
* **Navidrome** – music streaming server
* **Kavita** – digital library / ebook server
* **Nextcloud** – personal cloud storage and file sync
* **Dashboard** – centralized access to services
* **Flask-based utilities** – small internal tools

### Raspberry Pi 4 (DNS / Display)

* **Pi-hole** – network-wide DNS filtering and ad blocking
* **MagicMirror** – virtual calendar and display interface

### Raspberry Pi 4 (Energy System)

* **Venus OS (Victron)** – energy monitoring and control
* connected to MPPT controller
* fully operational monitoring setup

## Security and Hardening

* Nginx reverse proxy setup
* Fail2ban intrusion prevention
* custom filters for suspicious traffic
* periodic security audit reporting
* restricted exposure of services

## Automation and Operations

* automated backup system with snapshot rotation
* Telegram-based alerting for security events
* weekly security audit reporting
* automated system update workflow
* Git repository synchronization

## Design Principles

* keep services isolated and manageable
* automate repetitive tasks
* monitor system state continuously
* prefer simple and maintainable solutions
* document everything in a reusable format

## Goals

* maintain a stable and secure self-hosted environment
* learn practical Linux system administration
* experiment with infrastructure design on small hardware
* build a reusable knowledge base for future projects
* document real-world setups as part of a public portfolio

## Notes

This repository represents a real environment adapted into a public case study.

Sensitive information such as IP addresses, domain names, credentials, and internal network details has been removed or generalized.

AI tools (ChatGPT) were used for ideation, troubleshooting support, and documentation refinement, but all systems were configured, tested, and maintained manually.
