# Common Network Ports and Security Evaluation

This document outlines commonly used network ports, the services they are associated with, and a security evaluation of each. Monitoring and securing these ports is critical for hardening your network.

---

## 🔒 TCP Ports

| Port | Service                 | Description                          | Security Threat Evaluation                                  |
|------|-------------------------|--------------------------------------|-------------------------------------------------------------|
| 20   | FTP (Data)              | File Transfer Protocol (Data Channel) | Unencrypted, vulnerable to sniffing and MITM                |
| 21   | FTP (Control)           | File Transfer Protocol (Control)     | Same as above, plus brute-force login attempts              |
| 22   | SSH                     | Secure Shell                         | Generally secure; brute-force attacks and weak keys are risks |
| 23   | Telnet                  | Remote Login                         | **Highly insecure**, transmits data in plaintext            |
| 25   | SMTP                    | Simple Mail Transfer Protocol        | Open relays can be abused for spam; should be authenticated |
| 53   | DNS                     | Domain Name System                   | DNS amplification, poisoning, tunneling                     |
| 80   | HTTP                    | Web Traffic (Unencrypted)            | Susceptible to MITM, injection attacks                      |
| 110  | POP3                    | Email Retrieval (Unencrypted)        | Plaintext credentials; deprecated in secure environments    |
| 143  | IMAP                    | Email Retrieval (Unencrypted)        | Same as POP3; recommend using IMAPS                         |
| 443  | HTTPS                   | Secure Web Traffic                   | More secure than HTTP; vulnerabilities may exist in implementation |
| 445  | SMB                     | Server Message Block (Windows File Sharing) | Target of many ransomware and worm attacks (e.g., WannaCry) |
| 3306 | MySQL                   | Database                             | Should not be exposed publicly; risk of SQL injection       |
| 3389 | RDP                     | Remote Desktop Protocol              | Bruteforce, BlueKeep vulnerabilities                        |

---

## 📡 UDP Ports

| Port | Service                 | Description                          | Security Threat Evaluation                                  |
|------|-------------------------|--------------------------------------|-------------------------------------------------------------|
| 53   | DNS                     | Domain Name System                   | DNS amplification and tunneling attacks                     |
| 67   | DHCP (Server)           | Dynamic Host Configuration Protocol  | DHCP spoofing possible without port security                |
| 69   | TFTP                    | Trivial File Transfer Protocol       | No authentication; easily abused                            |
| 123  | NTP                     | Network Time Protocol                | NTP amplification DDoS attacks                              |
| 161  | SNMP                    | Simple Network Management Protocol   | Default community strings; info disclosure                  |
| 500  | IKE                     | Internet Key Exchange (VPNs)         | Vulnerable if weak keys or aggressive mode is enabled       |

---

## 🔐 Recommendations

- **Close unused ports** at the firewall and router level.
- **Use encrypted alternatives**: SSH instead of Telnet, HTTPS instead of HTTP, etc.
- **Enable logging and intrusion detection** systems to monitor these ports.
- **Change default credentials** and **enforce strong authentication mechanisms**.
- **Limit external exposure**: For example, database ports should never be publicly accessible.
- **Patch and update services regularly** to mitigate known vulnerabilities.

---

## 📚 Reference Tools

- `nmap` – Network scanner to detect open ports
- `netstat` – Inspect local port usage
- `iptables` / `ufw` – Linux firewalls to control port access
- `Wireshark` – Network traffic analyzer

