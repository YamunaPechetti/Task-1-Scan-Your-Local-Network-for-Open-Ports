# Task-1-Scan-Your-Local-Network-for-Open-Ports

## Objective: 
Learn to discover open ports on devices in your local network to understand network exposure.

---

## Tools used:
- [Nmap](https://nmap.org/) – for port scanning
- [Wireshark](https://www.wireshark.org/) – for packet analysis

---

## Steps performed:
1. **Identified Local IP Address**:
   - Used `ipconfig` to find local IP: `192.168.31.149`
   - Identified subnet: `192.168.31.0/24`

2. **Performed TCP SYN Scan**
   ```bash
   nmap -sS 192.168.31.0/24
   ```
3. **Saved Scanned Results**:
   - Saved the scanned results as `scan_results.txt`
4. **Packet Capture with Wireshark**:
   - Captured packets during the Nmap scan for deeper inspection.
