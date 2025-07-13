# 🛡️ SOC Lab 01 – SSH Brute Force + Reverse Shell Detection

Simulated brute force attack on SSH followed by reverse shell and persistence via cron and bashrc. Detection was done using Wazuh agent & manager, followed by manual threat hunting and cleanup.

---

## 🔥 Attack Overview

- Brute force via `hydra` on port 22
- Reverse shell using `bash -i >& /dev/tcp/...`
- Persistence via:
  - Cronjob with malicious `backup.sh`
  - PATH hijack using fake binary `cp`
- Privilege escalation through misconfigured user and environment
- Cleanup and full system recovery steps included

---

## 🔍 Detection & Threat Hunting

- Wazuh Agent alerts (custom rule)
- Manual hunting in `.bash_history`, crontab, `/tmp`, `/usr/local/bin`
- Wireshark analysis for reverse shell traffic
- IOC mapping and root cause analysis

---

## 🧹 Remediation

- Removed malicious cronjob & scripts
- Deleted fake binaries in `/tmp`
- Locked compromised user
- Ran `chkrootkit` and `rkhunter` scans
- Reset passwords, verified `.bashrc` & `authorized_keys`

---

## 📂 Files & Documentation

- 📄 [Full Report (PDF)](https://drive.google.com/file/d/1n64Er-_OHhs_NZYD31HbZPKbs0Mb--bo/view?usp=drive_link)
- 📘 [Full TOC version available in GDoc here](https://docs.google.com/document/d/1CVfDZTuOEb2MJw0WkZrOI94V3nAKwzYkoinYQAgXbMQ/edit?usp=sharing)
- 📸 Screenshots in `screenshots/`
- 🧪 Hunting notes in `hunting/`
- 🛡️ Detection config in `detection/`
- 🧹 Remediation flow in `remediation/`

---

> _This lab simulates a real-world attack chain and shows how to detect, investigate, and respond using open-source tools like Wazuh._

---

## 🖋️ Report by Kamii (Hashim Zulkifli)

Built, simulated, hunted, and documented by Kamii – a cybersecurity learner focused on real-world SOC labs, threat hunting, and detection engineering.

Part of an ongoing journey to simulate attack chains, investigate deeply, and defend calmly.

🔗 [GitHub](https://github.com/Kamii-cxo)  
🔗 [LinkedIn](https://linkedin.com/in/hashim-zulkifli)  
📂 [Cybersecurity Portfolio Vault](https://drive.google.com/drive/folders/17wl9kDajrwSZJJOf9uIVusCxLa_jdcz7?usp=drive_link)

> _"Real labs. Real learning. One command at a time."_

