# Watchtower Stack

![Stack](https://img.shields.io/badge/stack-Wazuh%20%7C%20Security%20Onion%20%7C%20Grafana-blue)
![Platform](https://img.shields.io/badge/platform-Proxmox%20VE-e57000)
![License](https://img.shields.io/badge/license-GPLv3-blue)

Configuration files, scripts, and documentation for the Watchtower Stack — a Proxmox-based home/lab SOC platform with full packet capture, endpoint detection, and long-term forensic storage.

> "The shrewd one sees the danger and conceals himself"

## Stack overview

| Component | Role |
|---|---|
| Security Onion | Network IDS, full packet capture (Suricata, Zeek, Stenographer) |
| Wazuh | Endpoint detection, file integrity, custom rules |
| Grafana | Dashboards and alerting (Discord, Teams, email) |
| Prometheus | Mission-critical host metrics (CPU, RAM, disk, services) |
| Dashy | Unified portal |
| Arpwatch | ARP table monitoring (optional) |

Welcome to the Watchtower Stack repository. This repository houses configuration files, scripts, and other essential information for the Watchtower Stack, a robust hardware server cluster powered by the Linux-based, free, and open-source hypervisor, Proxmox Virtual Environment.

### Overview

Watchtower is meticulously designed to offer comprehensive visibility into your network, coupled with advanced alerting capabilities based on network traffic and system telemetry. This ensures top-notch network security by ingesting data from endpoints and the network itself.

### Stack Features

1. Network intrusion detection and monitoring via Security Onion
2. Full packet capture via Stenographer
3. Full endpoint event visibility via Wazuh
4. Automatic file hash inspection for downloaded files with VirusTotal
5. Instantaneous status monitoring for mission-critical systems via Prometheus
6. Automatic software inventory system via Wazuh
7. ARP table monitoring via Arpwatch (optional)
8. Easy-to-use interface via custom HTML and Dashy
9. Ultra-long-term forensic storage of network connections indexed by Zeek via the Watchtower-Forensic Datastore
10. A global dashboard to monitor network and system status from all data ingest points via Grafana
11. So much more! (Wow!)

### Virtual Machines

Here are the key virtual machines that constitute the Watchtower Stack:

1. **Vashti:**
   - Prometheus Database
      - Collects real-time information from mission-critical servers
      - RAM, CPU, Network, Disk, Windows Services, and more
   - HTTPd for piping data into Elasticsearch
   - Blackbox for Prometheus

2. **Jehoahaz:**
   - Grafana for alerting
      - Allows the creation of custom alerts from Prometheus and Elastic
      - Send alerts to Discord, Teams, email, and more

3. **Hezekiah:**
   - Wazuh Stack
        - Monitors endpoint events
        - Custom rules allow for monitoring directories, file tampering, etc.
        - Alerts to email and SMS via email-to-SMS relay services
   - Postfix

4. **Korah:**
   - Dashy
   - ICMP Status Checker

5. **David:**
   - Security Onion
     - Main data ingest virtual machine
     - ELK Stack
     - Redis
     - Suricata
     - Zeek
     - Strelka
     - Stenographer

6. **Manasseh:**
   - Ubuntu Server Installation
     - Maintains extremely long-term historical data on network connections (over ten years capacity expected)

### Watchtower Stack Data Flow

![Watchtower Data Flow](https://i.imgur.com/3dDJ9Of.jpg)


