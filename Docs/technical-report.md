# Technical Cybersecurity Project Report



**Enterprise Web Application Defense Platform — Nginx WAF, ModSecurity & OWASP CRS**

## Summary

This project implements a layered web-application defense architecture in which Nginx operates as a reverse proxy between clients and a backend web server. ModSecurity and OWASP CRS inspect inbound requests and provide detection/blocking of common web attacks. DNS and TLS provide controlled application access and encrypted client-to-WAF communication.

The security program was extended with Nmap network/service discovery, OpenVAS vulnerability assessment, Lynis Linux security auditing and hardening, file-integrity monitoring, and operational log analysis.

## Implementation Procedure

1. Designed separate WAF and backend network zones.
2. Deployed and configured the backend web server.
3. Configured DNS so the application name resolves to the WAF.
4. Secured the client-to-WAF path using TLS.
5. Configured Nginx as the reverse proxy.
6. Integrated ModSecurity and OWASP CRS.
7. Validated normal traffic and authorized attack simulations.
8. Monitored Nginx and ModSecurity audit logs.
9. Performed Nmap service/attack-surface assessment.
10. Performed OpenVAS vulnerability assessment.
11. Applied Linux hardening based on Lynis findings.
12. Implemented file-integrity monitoring and retested controls.

## Architecture


Client / Kali linux
       |
       | HTTPS
       v
WAF: Nginx + ModSecurity + OWASP CRS
       |
       | HTTP/HTTPS
       v
Backend Web Server
       |
       v
Application
``

## Results

| Control | Result |
|---|---|
| Nginx reverse proxy | Implemented |
| TLS | Implemented |
| DNS | Implemented |
| ModSecurity | Implemented |
| OWASP CRS | Implemented |
| WAF security validation | Completed |
| Nmap assessment | Completed |
| OpenVAS assessment | Completed |
| Lynis hardening | Completed |
| FIM | Implemented |
| Security-log monitoring | Implemented |

Replace result labels with exact evidence before final publication.

## Security Outcome

The project demonstrates defense in depth by combining prevention, detection, vulnerability management, operating-system hardening, integrity monitoring, and security-log analysis.

## Resume Description

Designed and implemented a layered enterprise web-application defense platform using Nginx reverse proxy, ModSecurity, OWASP CRS, TLS, DNS, vulnerability assessment with Nmap/OpenVAS, Linux hardening with Lynis, file-integrity monitoring, security logging, and authorized WAF validation.
