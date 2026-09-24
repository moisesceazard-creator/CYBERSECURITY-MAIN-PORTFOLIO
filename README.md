# Moises Ceazar Del Mundo — Cybersecurity Portfolio

A single-page personal portfolio website showcasing hands-on SOC (Security Operations Center) analyst work — home lab builds, incident investigation write-ups, and cybersecurity certifications.

🔗 **Live site:** _(add your GitHub Pages / hosting link here)_

## What's on the site

### 🏠 Hero / Intro
Quick landing section introducing who I am and what I do.

### 🧪 Lab Projects
Hands-on environments simulating real SOC workflows:
- **Security Operations Home Lab** — Security Onion SIEM, Zeek/Suricata alert monitoring, Kibana dashboards, T-Pot honeypot for observing live attacker behavior.
- **Wazuh SIEM & Endpoint Monitoring Lab** — Wazuh agents deployed across multiple VMs in Proxmox VE for centralized endpoint monitoring, with custom dashboards for event visualization and log correlation.
- **LetsDefend SOC Investigation Write-ups** — structured Tier 1 SOC investigations covering alert triage, phishing email analysis, malware investigation, and incident handling, documented in formal SOC analyst report format.

### 📜 Certifications & Badges
A tabbed, clickable grid of earned certificates and LetsDefend training badges, each opening a full-size preview on click.

## Tech Stack

- Plain **HTML, CSS, and JavaScript** — no frameworks, no build step
- Certificate/badge images embedded inline as base64 `data:` URLs (fully self-contained, no external image hosting needed)
- CSS Grid for responsive card layouts
- Scroll-triggered reveal animations

## Running Locally

No build tools required — just open `index.html` directly in a browser, or serve it with any static file server:

```bash
python3 -m http.server
```

## Project/Repo Links Referenced on the Site

- [SOC-Incident-Writeups](https://github.com/moisesceazard-creator/SOC-Incident-Writeups.git) — detailed case write-ups (alert triage, MITRE ATT&CK mapping, containment actions)
- [Security-Onion-Telegram-Alerting](https://github.com/moisesceazard-creator/Security-Onion-Telegram-Alerting)
- [Wazuh-SIEM-Endpoint-Monitoring-Lab](https://github.com/moisesceazard-creator/Wazuh-SIEM-Endpoint-Monitoring-Lab)
- [Nessus-Vulnerability-Assessment-Lab](https://github.com/moisesceazard-creator/Nessus-Vulnerability-Assessment-Lab)

## Maintenance Notes

- File is large due to embedded base64 images — when editing, search for specific class names/sections rather than viewing the whole file at once.
- When adding cards to `.projects-grid` or `.certs-grid`, make sure each card's closing `</div>` is correctly nested and the grid container closes only after the **last** card.
