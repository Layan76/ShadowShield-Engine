## 🛡️ShadowShield-Engine — SOC Threat Detection & Decision Engine 

**SOC Threat Detection & Security Decision Engine**

ShadowShield-Engine is a cybersecurity threat detection and decision-support prototype designed to analyze network activity, identify abnormal traffic patterns, classify security risks, and generate structured security events for SOC-oriented monitoring and analysis.

The project focuses on practical defensive security concepts including threat detection, network security monitoring, risk classification, security event logging, and automated security decision-making.

---

## 📌 Project Overview

ShadowShield-Engine provides a structured security monitoring pipeline for detecting and evaluating suspicious network activity.

The system analyzes traffic-related events, identifies abnormal behavior based on predefined detection logic, assigns a risk level, and generates an appropriate security decision.

### Risk Levels

- LOW
- MEDIUM
- HIGH

### Security Actions

- ALLOW
- ALERT
- BLOCK

Each security decision is recorded as a structured JSON event containing relevant information such as the source IP address, detection rule, traffic metrics, risk level, recommended action, and timestamp.

The project is designed as a practical cybersecurity prototype that can be extended with IDS telemetry, SIEM integration, additional detection rules, and automated response capabilities.

---

## 🏗️ Architecture

The current ShadowShield-Engine workflow follows this structure:

Network Activity  
↓  
Detection Engine  
↓  
Decision Engine  
↓  
Risk Classification  
↓  
Security Action  
↓  
Structured JSON Logging

### Planned IDS Integration

The next development stage will integrate Suricata IDS telemetry:

Suricata  
↓  
eve.json  
↓  
ShadowShield Detection Engine  
↓  
Decision Engine  
↓  
Risk Classification  
↓  
Security Logs  
↓  
Future Dashboard / SIEM Integration

---

## 🔍 Core Components

### 1. Detection Engine

The Detection Engine analyzes network-related activity using predefined detection logic to identify abnormal traffic patterns.

The current implementation focuses on identifying unusual traffic behavior associated with individual source IP addresses using traffic metrics such as packets per minute.

The detection layer is designed to be expandable so additional security detection rules can be introduced in future versions.

---

### 2. Decision Engine

The Decision Engine converts detection results into structured, human-readable security decisions.

Each generated security decision can contain:

- `rule_name`
- `src_ip`
- `packets_per_min`
- `risk_level`
- `action`
- `timestamp`

Based on the detected activity, the engine assigns a risk level and determines an appropriate security action:

- `ALLOW`
- `ALERT`
- `BLOCK`

This provides a structured method for translating detection results into actionable security information.

---

### 3. Logging Layer

Every security decision is written as a structured JSON record to:

`shadowshield_events.log`

The logging layer enables security events to be:

- Parsed
- Reviewed
- Analyzed
- Visualized
- Forwarded to other security monitoring tools in future versions

Structured logging also provides a foundation for future SIEM integration and security analytics.

---

## 🛠️ Technologies & Security Concepts

### Technologies

- Python
- JSON
- Structured Security Logging

### Cybersecurity Concepts

- SOC Monitoring
- Threat Detection
- Network Traffic Analysis
- Security Event Analysis
- Risk Classification
- Detection Engineering Fundamentals
- Security Monitoring
- Defensive Security
- Incident Detection

### Planned Integration

- Suricata IDS
- `eve.json` Telemetry
- SIEM Integration
- Security Monitoring Dashboard

---

## 📊 Current Status — TRL 3

ShadowShield-Engine is currently at **Technology Readiness Level (TRL) 3**, progressing toward **TRL 4**.

### Current Implementation

The core concept has been implemented and validated using controlled synthetic test data.

The following core components currently work together:

- Detection logic
- Security decision generation
- Risk classification
- Structured JSON security logging

The system can process defined security test cases and generate structured security decisions.

---

## 🚀 Moving Toward TRL 4

The next major development stage is integrating ShadowShield-Engine with a real IDS sensor using **Suricata**.

The planned integration will read network security events from Suricata's:

`eve.json`

This will allow ShadowShield-Engine to process real network telemetry within a controlled lab environment.

The objective is to evaluate the detection and decision pipeline against realistic network activity rather than relying only on synthetic test cases.

Once the Suricata integration is completed and validated against network traffic in a controlled lab environment, the prototype can progress toward **TRL 4 validation**.

---

## 🔮 Future Work

Planned improvements include:

- Integrate Suricata `eve.json` for real network telemetry.
- Expand detection coverage for additional suspicious behaviors.
- Add detection logic for port scanning.
- Add detection logic for brute-force activity.
- Explore detection of suspicious DNS activity.
- Improve risk classification logic.
- Develop automated response capabilities.
- Explore automated IP blocking through firewall rules.
- Build a security monitoring dashboard.
- Visualize security events and detection decisions.
- Explore SIEM integration for centralized event monitoring and analysis.

---

## 🧪 Testing

The current prototype has been tested using controlled synthetic security test cases defined within the project.

Testing is focused on validating the complete processing pipeline:

Input Security Event  
↓  
Detection  
↓  
Risk Classification  
↓  
Security Decision  
↓  
JSON Log Generation

Future testing will use Suricata-generated network telemetry in a controlled lab environment.

---

## 📄 Security Event Output

ShadowShield-Engine generates structured security events containing fields such as:

- Detection rule
- Source IP
- Traffic metrics
- Risk level
- Security action
- UTC timestamp

Security events are stored in:

`shadowshield_events.log`

This structured format is intended to support security analysis and future integration with monitoring and SIEM platforms.

---

## 🎯 Project Purpose

ShadowShield-Engine was developed as a hands-on cybersecurity project to strengthen practical skills in:

- SOC operations
- Threat detection
- Network security monitoring
- Security event analysis
- Risk-based security decision-making
- Security logging
- Detection engineering
- Defensive security engineering

The project demonstrates the design of a basic security monitoring pipeline from detection through decision-making and structured event generation.

---

## 📈 Development Roadmap

### Phase 1 — Core Engine ✅

- Detection logic
- Risk classification
- Decision engine
- JSON security logging
- Synthetic test cases

### Phase 2 — IDS Integration 🚧

- Suricata deployment
- `eve.json` ingestion
- Real network event processing
- Controlled lab testing

### Phase 3 — Detection Expansion 📋

- Port scan detection
- Brute-force detection
- DNS-related detection
- Additional network security rules

### Phase 4 — Monitoring & Response 📋

- Security monitoring dashboard
- Event visualization
- SIEM integration
- Automated response capabilities

---

## ⚠️ Project Status

This project is currently under active development.

Some capabilities described in the roadmap, including Suricata integration, SIEM integration, dashboard development, and automated response, are planned features and are not part of the current implementation.

---

## 👩‍💻 Author

**Layan Mohammed Abdulaziz**

Computer Science | Cybersecurity | SOC | Threat Detection | Risk Management- Build a simple web/dashboard interface to visualize ShadowShield decisions and network events.
