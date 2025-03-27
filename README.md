# 🛡️ Intrusion Detection with Snort and PulledPork3

This project demonstrates how to detect malware and analyze network traffic using **Snort 3** and **PulledPork3** on Kali Linux. A real-world PCAP file from [malware-traffic-analysis.net](https://www.malware-traffic-analysis.net/) was used to extract alerts, apply Snort rules, and detect malicious patterns including **Win.Trojan.WhisperGate**.

---

## 🚀 Tools & Technologies

- 🐚 Kali Linux VM  
- 🧠 Snort 3 (Snort++)  
- 🐷 PulledPork3  
- 🔎 PCAP file from malware-traffic-analysis.net  
- 🧰 CLI tools: `grep`, `cut`, `uniq`, `sort`, `nano`, `wget`  
- 📡 Network Adapter Configuration with `ethtool`

---

## 📁 Project Highlights

- Installed and configured **Snort 3** with custom rule sets
- Integrated **PulledPork3** for automated rule management
- Used **ICMP detection**, port scanning, and HTTP inspection
- Detected malware using **Snort signatures**
- Wrote custom Snort rules in `local.rules`
- Parsed output using command-line tools to sort and find signature patterns

---

## 🧪 Commands Used

```bash
snort -c /usr/local/etc/snort/snort.lua -R /usr/local/etc/rules/local.rules -r traffic.pcap -A alert_fast

cat pcap-signatures.txt | cut -d "]" -f 3 | cut -d "[" -f 1 | cut -d '"' -f 2 | sort | uniq -c | sort -nr

