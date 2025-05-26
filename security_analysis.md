# Security Analysis

## Open Ports Identified
| Hostname                    | IP Address       | Open Ports                          | Services                                |
|-----------------------------|------------------|-------------------------------------|-----------------------------------------|
| Wi-Fi                       | 192.168.31.1     | 53, 80, 443, 7443, 8080, 8443       | DNS, HTTP, HTTPS, OracleAS, Proxy HTTP  |
| Phone                       | 192.168.31.60    | None                                | All scanned ports are closed            |
| Laptop/Desktop              | 192.168.31.149   | 135, 139, 445, 902, 912, 5432, 8080 | MSRPC, NetBIOS, SMB, PostgreSQL, etc.   |

---

## Potential Security Risks

- **192.168.31.1 (Router/Gateway)**
  - Port **80/443/8080/8443**: If the web interface is exposed and not password protected, it may be vulnerable to unauthorized access or CSRF attacks.
  - Port **7443**: Often used by management interfaces — could be sensitive if not restricted.
  - Port **53**: Open DNS services may allow DNS amplification attacks if misconfigured.

- **192.168.31.149 (Desktop)**
  - Ports **135, 139, 445**: Windows services often targeted for SMB relay attacks, EternalBlue, and lateral movement.
  - Port **5432**: PostgreSQL — if exposed without authentication, attackers could access or modify databases.
  - Port **902/912**: Possibly related to VMware or remote services — further inspection needed.
  - Port **8080**: Alternate web service — could run test/development apps vulnerable to exploits.

- **192.168.31.60 (Phone)**
  - No open ports — safe as per this scan.
