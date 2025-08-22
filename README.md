# Cyberversus

# 🛡️ Cyber Threat Intelligence & Simulation Platform

## 🌍 Live DDoS Attack Map with Honeypot, Red/Blue Team Simulation & Threat Intelligence

A full-stack, containerized cyber threat platform designed for:
- Real-time DDoS visualization
- Honeypot logging & alerting
- Red/Blue team simulation
- MITRE ATT&CK mapping
- Malware artifact collection
- Threat actor profiling
- SOAR-like automation
- Community-based intelligence sharing
- AI-based anomaly detection

> Built for researchers, cybersecurity students, blue teamers, red teamers, and analysts.

---

## 🔧 Features Overview

### 📡 Live DDoS Attack Map
- Real-time attack arcs and source geolocation
- Public data feeds + private honeypot data
- Mapbox or Globe.gl support

### 🧲 Honeypot Integration
- Cowrie + Dionaea support
- Captures attacker IPs, commands, and attempted downloads
- Real-time WebSocket event streaming

### 🧠 AI-Based Anomaly Detection
- Flags unusual behavior, spikes, new ports/protocols
- Uses LSTM, Isolation Forest, or Prophet
- Risk scoring per IP or session


### 🔵🔴 Red / Blue Team Simulation Playground
- Red team: Simulate attacks (e.g., HTTP flood, SSH brute)
- Blue team: Respond via IP blocking, mitigation scripts
- Scoring system for training & challenges

### 👨‍💻 Honeypot Network Graph
- Graph of attacker IPs and targeted services
- Clustered by behavior, geolocation, or ASN
- Real-time, interactive graph (Cytoscape.js)

### 🧩 Plugin System
- Easily extend the platform with:
  - New sensors
  - Threat feeds
  - Visualization types
  - Detection models

---

## 🔬 Threat Intelligence Features

### 🔬 MITRE ATT&CK Mapping
- Automatic mapping of observed techniques
- JSON + PDF/Markdown export
- Daily summary reports and session-based views
- Example:
  - T1110 - Brute Force (SSH)
  - T1059 - Command & Scripting Interpreter

### 🧬 Threat Actor Profiling
- Cluster attackers based on behavior, tools, and ASN
- Track reputation, enrichment with Shodan/IPInfo
- View "historical footprints" per actor

### 🦠 Malware Artifact Collection
- Dionaea honeypot integration
- Captures malware binaries
- Auto hashes (SHA256) and scans via VirusTotal API
- Stores filetype, timestamp, origin IP

### 🤖 SOAR-Like Security Automation
- Define rules (e.g., auto-block if IP attempts > 10)
- Send reports to AbuseIPDB, block via firewall
- Discord/Telegram/Slack alerting

---

## 📂 Data Export & Reporting

### 📄 PDF / Markdown Report Generator
- Daily attack reports
- Includes:
  - MITRE mapping
  - Top IPs
  - Country breakdown
  - Network graph snapshot
  - Anomalies flagged

### 📁 Raw Log Explorer
- Elastic-style filterable view
- Search by IP, command, protocol, or country
- Export logs to JSON or CSV

### 🔓 Open Threat Feed API
- `GET /api/threats/latest`
- `GET /api/threats/search?ip=...`
- `GET /api/threats/geo?country=...`
- Public and private access options

---

## 🛠️ Tech Stack

| Layer         | Stack                       |
|---------------|-----------------------------|
| Frontend      | React.js + Cytoscape.js     |
| Backend       | FastAPI or Node.js          |
| ML/AI Engine  | Python (scikit-learn, Prophet) |
| Database      | MongoDB / PostgreSQL        |
| Honeypots     | Cowrie, Dionaea             |
| Alerting      | Telegram, Discord, Email    |
| Containerization | Docker + Kubernetes       |

---

## 📦 Microservice Architecture

- `frontend`: UI for map, dashboards, and logs
- `backend-api`: REST API + WebSocket for real-time events
- `honeypot-parser`: Reads logs and submits events
- `ai-engine`: Runs anomaly detection and risk scoring
- `alert-engine`: Sends notifications based on rules
- `graph-api`: Returns data for attack graphs
- `open-threat-api`: Public-facing threat data
- `community-dashboard`: Contributor stats & feed

## Services:

- frontend
- backend-api
- db
- ai-engine
- honeypot-parser
- alert-engine
- threat-api

## ☸️ Kubernetes / Docker Support

## Sample Use Case: Red/Blue Team Simulation

### Red team simulates attack:

- POST /simulate/attack → Sends fake DDoS to honeypot

### Blue team dashboard detects:

- Live graph arc appears
- New event in "Live Threats"

### Blue team responds:
- Click "Block IP"
- System adds IP to blocklist + AbuseIPDB

### AI engine:
- Flags attacker behavior as suspicious
- Risk score increased
## 🔐 Security Notes

- All honeypots run in isolated containers/VPS
-Public API access is read-only
- Admin panel protected by JWT + Role-Based Access
- All data sanitized on ingest
- Threat sharing opt-in for community

## 📢 Contributions
- Fork, clone, and PR!
- Ideas for new plugins, ML models, or sensors are welcome.
- See /docs/plugins.md for the plugin developer guide.

## 🧾 License
- MIT License © 2025 YourName or Org

## 🔗 Links
-  📘 MITRE ATT&CK Framework
- 📡 Cowrie Honeypot
- 🧠 Cytoscape.js
- 🤖 Prophet Forecasting
- 🧪 VirusTotal API
