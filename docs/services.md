# Services

## Overview

This document provides an overview of the services running in the self-hosted Raspberry Pi infrastructure.

Each service has a specific role and contributes to the overall functionality of the system.

## Application Services (Raspberry Pi 5)

### Immich

* self-hosted photo and media management platform
* used for storing and browsing personal media
* provides web-based access and organization features

### Navidrome

* lightweight music streaming server
* serves a personal music library over the network
* supports browser-based playback and API clients

### Kavita

* digital library and ebook server
* used for managing and reading books and comics
* accessible through a web interface

### Nextcloud

* personal cloud storage and file synchronization platform
* used for file storage, sharing, and remote access
* supports multiple clients and integrations

### Dashboard

* centralized entry point for accessing services
* improves usability and visibility of the environment
* reduces the need to remember service URLs

### Flask-based utilities

* small custom applications for internal use
* used for lightweight tools and experiments
* deployed via Nginx and uWSGI

## Network and Display Services (Raspberry Pi 4)

### Pi-hole

* network-wide DNS filtering and ad blocking
* improves privacy and reduces unwanted traffic
* provides visibility into DNS queries

### MagicMirror

* dashboard-style display interface
* used for calendar and system visibility
* runs as a local visual information panel

## Energy System (Raspberry Pi 4)

### Venus OS (Victron)

* dedicated energy monitoring system
* connected to MPPT controller
* provides real-time data on energy production and usage

## Supporting Infrastructure

These components support the services above:

* Nginx (reverse proxy and routing)
* Fail2ban (intrusion prevention)
* backup system (snapshot-based)
* audit system (periodic checks)
* update automation (multi-source package updates)
* notification system (Telegram alerts)

## Summary

The services are organized to provide:

* media management
* personal cloud functionality
* network-level control
* monitoring and visibility
* operational reliability

Each component plays a specific role within the overall infrastructure.
