## Azure East-West Traffic Segmentation & Lateral Movement Simulation
## Overview
This project simulates a real-world Azure security scenario where a compromised management server attempts to access production resources through Azure VNet Peering.

## The project demonstrates:

Host Discovery
Service Enumeration
Traffic Analysis
Lateral Movement
Network Segmentation
Azure NSG Enforcement
Azure Network Watcher Validation
## Architecture
Management Network (Attacker VM)
            │
            │ Azure VNet Peering
            ▼
Production Network (Target VM)
            │
            ├── Internal Business Portal
            ├── Sample Payroll Data
            └── NSG Protection
            
Phase 1 - VNet Peering
![Alt Text](assets/vnet-peering.png)


Established connectivity between isolated Azure virtual networks.

Phase 2 - Simulated Sensitive Data
Payroll Data

Created synthetic payroll data to represent business-critical information hosted in a production environment.

Phase 3 - Internal Business Portal
Business Portal

Deployed an internal business portal using Apache on Linux.

Phase 4 - Service Enumeration
Nmap Enumeration

Performed host discovery and service enumeration using Nmap.

Phase 5 - Traffic Analysis
Tcpdump Analysis

Captured east-west traffic between peered environments using tcpdump.

Phase 6 - Lateral Movement Validation
SSH Reachability

Validated SSH reachability before security controls were implemented.

Phase 7 - Application Access
Portal Access

Successfully accessed the internal business application from the management network.

Phase 8 - NSG Segmentation Controls
NSG Rules

Implemented segmentation controls:

Allow HTTP (80)
Deny SSH (22)
Phase 9 - SSH Blocked
SSH Blocked

Confirmed lateral movement was prevented after NSG implementation.

Phase 10 - Azure Validation
SSH Blocked
Network Watcher SSH

Azure Network Watcher confirmed SSH communication was blocked.

HTTP Allowed
Network Watcher HTTP

Azure Network Watcher confirmed business application traffic remained reachable.

## Key Findings
VNet Peering enables communication between isolated Azure networks.
SSH and HTTP services were accessible through peering before segmentation controls.
NSGs successfully blocked administrative access.
Business application availability was preserved.
Azure Network Watcher provided native validation of security controls.
## Disclaimer
This project was created in a controlled Azure lab environment using synthetic data for educational and security testing purposes.

No production workloads, customer information, credentials, or organizational
