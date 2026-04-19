# Operations

## Overview

This document describes the operational workflows used to maintain and monitor the self-hosted infrastructure.

The focus is on automation, reliability, and reducing manual intervention.

## Backup Workflow

The system uses an automated backup process:

* data is transferred over SSH to a remote location
* snapshots are created using timestamp-based directories
* a "latest" symlink points to the newest backup
* older snapshots are removed based on a retention policy

Benefits:

* predictable recovery points
* controlled storage usage
* minimal manual intervention

## System Update Workflow

A unified update script handles multiple package ecosystems:

* APT (system packages)
* Snap
* Flatpak
* pipx (Python tools)
* Docker (engine and images)
* Git repositories

Features:

* fallback logic for failed updates
* automatic cleanup (e.g. Docker images)
* consistent update process across environments

## Security Monitoring

Security is handled through multiple mechanisms:

* Fail2ban monitors logs and blocks suspicious IP addresses
* custom filters detect common attack patterns
* Nginx hardening reduces exposure
* restricted access to sensitive endpoints

## Audit Workflow

A scheduled audit script performs periodic checks:

* login activity (successful and failed)
* user account changes
* cron configuration changes
* systemd service changes
* setuid file changes

Results are:

* compared against a baseline
* summarized in a report
* delivered via email

## Notification System

Important events are surfaced through notifications:

* Fail2ban triggers Telegram alerts
* backup jobs report success or failure
* audit reports provide periodic summaries

This reduces the need for manual monitoring.

## Operational Philosophy

The system follows a simple operational model:

```text
Automate → Monitor → Detect → Respond → Improve
```

Key principles:

* automate repetitive tasks
* make system state visible
* detect changes early
* respond to issues quickly
* continuously refine the setup

## Summary

The operational layer ensures that the infrastructure remains:

* reliable
* observable
* maintainable

Automation and monitoring work together to reduce manual effort and improve system stability.
