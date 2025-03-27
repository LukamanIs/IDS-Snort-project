# Snort + PulledPork3 Malware Detection Project

This project demonstrates malware traffic analysis using Snort++ and PulledPork3 on a Kali Linux VM.

## Tools Used
- **Snort 3**: Intrusion Detection System
- **PulledPork 3**: Rule management
- **PCAP**: Sample from malware-traffic-analysis.net
- **Wireshark / CLI Tools** for analysis

## Key Steps
1. Setup Snort 3 and install dependencies
2. Install and configure PulledPork3 with oinkcode
3. Download and unzip PCAP file
4. Run Snort against PCAP file
5. Parse and analyze alert output
6. Extract and sort signatures using:
   ```bash
   cat pcap-signatures.txt | cut -d "]" -f 3 | cut -d "[" -f 1 | cut -d '"' -f 2 | sort | uniq -c | sort -nr
