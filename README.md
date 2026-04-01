# ShadowShield-Engine

ShadowShield-Engine is a lightweight home network defense prototype that combines a detection engine, decision engine, and structured security logging to monitor and react to abnormal traffic patterns.

## Project Overview

This project aims to provide an intelligent security layer for small / home networks.  
The system monitors network activity, detects traffic spikes for each source IP, classifies the risk level (LOW / MEDIUM / HIGH), and generates a corresponding security decision (ALLOW / ALERT / BLOCK) with a precise timestamp.

All decisions are stored in a unified JSON log file (shadowshield_events.log), which can later be analyzed or visualized in a dashboard or SIEM-like interface.

## Components

- **Detection Engine**  
  Custom logic to detect abnormal traffic (e.g., traffic spikes) per source IP using simple metrics such as packets per minute.

- **Decision Engine**  
  Translates detection results into human-readable security decisions, including:  
  - rule_name  
  - src_ip  
  - packets_per_min  
  - risk_level  
  - action (ALLOW / ALERT / BLOCK)  
  - timestamp (UTC, ISO 8601 format)

- **Logging Layer**  
  Every decision is written as a separate JSON record to `shadowshield_events.log`, making it easy to parse, analyze, or forward to other tools.

## Current Status (TRL Level)

The project is currently between **TRL 3 and TRL 4**:

- At **TRL 3**:  
  - The core concept has been implemented and validated using synthetic test data (test cases defined in code).  
  - The detection and decision engines work together and generate structured JSON logs.

- Moving into **TRL 4**:  
  - The next step is to integrate ShadowShield-Engine with a real IDS sensor (Suricata) by reading live network events from the `eve.json` file in a controlled lab environment (home / test network).  
  - This will allow the prototype to operate on real network traffic, detect abnormal behavior, and log real-world security decisions.

Once the integration with Suricata is complete and tested on real traffic in a lab environment, ShadowShield-Engine can be formally considered a **TRL 4** prototype: a working implementation validated in a controlled environment.

## Future Work

- Integrate with Suricata `eve.json` for real traffic input.  
- Add more detection rules (brute-force attempts, port scanning, DNS abuse, etc.).  
- Implement automated responses (e.g., blocking IPs via firewall rules).  
- Build a simple web/dashboard interface to visualize ShadowShield decisions and network events.
