# Lessons Learned

## Overview

This document summarizes key lessons learned while building and maintaining a self-hosted Raspberry Pi infrastructure.

The focus is not only on what was implemented, but on practical insights gained through real-world usage, troubleshooting, and continuous iteration.

## 1. Real systems are always evolving

Even when a system appears stable, it is constantly changing:

* services update
* configurations drift
* new dependencies appear
* logs reveal unexpected behavior

A working setup is not a final state, but an ongoing process of monitoring and adjustment.

## 2. Visibility is more important than complexity

Adding more tools does not necessarily improve reliability.

What matters more is:

* being able to see what is happening
* having clear logs and reports
* understanding system behavior over time

This led to building audit scripts and notification systems instead of relying only on passive logs.

## 3. Automation reduces human error

Manual tasks such as:

* backups
* system updates
* log checks

are easy to forget or perform inconsistently.

Automating these processes:

* improves reliability
* reduces cognitive load
* creates predictable system behavior

## 4. Security is about layers, not a single tool

There is no single solution that secures a system.

A more effective approach is layered:

* Nginx hardening
* Fail2ban rules and custom filters
* periodic security audits
* restricted exposure of services

Each layer reduces risk incrementally.

## 5. Small devices can run meaningful infrastructure

Raspberry Pi hardware is capable of running:

* media servers
* cloud storage
* DNS filtering
* dashboards
* automation workflows

The limitation is not the hardware, but how services are configured and managed.

## 6. Simplicity improves maintainability

Simple, well-understood solutions are easier to maintain than complex setups.

Examples:

* using Bash scripts instead of heavy frameworks
* separating services clearly
* avoiding unnecessary dependencies

This reduces the risk of breakage and makes troubleshooting easier.

## 7. Troubleshooting builds real understanding

Most practical knowledge came from:

* debugging broken configurations
* fixing service failures
* analyzing logs
* iterating on scripts

Working through failures provided more value than initial setup.

## 8. Documentation turns experience into reusable knowledge

Without documentation, solutions remain isolated.

By documenting:

* configurations
* workflows
* decisions

the system becomes:

* easier to maintain
* easier to extend
* easier to explain to others

## 9. AI is a tool, not a replacement

AI tools were helpful for:

* generating ideas
* debugging issues
* refining scripts
* structuring documentation

However, the final system required:

* manual testing
* real-world validation
* understanding of how components interact

## 10. Infrastructure thinking is a skill

This project evolved from individual setups into a broader understanding of:

* system architecture
* service relationships
* reliability and maintenance
* operational workflows

The most important takeaway is not any single tool, but the ability to design and maintain a functioning system as a whole.
