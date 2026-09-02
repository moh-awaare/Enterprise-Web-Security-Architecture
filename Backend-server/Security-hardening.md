## File Integrity Monitoring

FIM helps identify unexpected changes to high-value files.

Candidate paths:

```text
/etc/nginx/
/etc/ssh/
/etc/systemd/
/var/www/
```

Record monitored path, baseline date, expected changes, detected changes, investigation, and remediation.


## lynis Audit system ##

# Linux Hardening with Lynis

Run:

```bash
sudo lynis audit system
```

Review warnings and suggestions covering services, authentication, permissions, logging, kernel/security settings, and filesystem configuration.

Workflow:

```text
Baseline -> Lynis audit -> Remediation -> Re-audit -> Compare
```

Document each remediation and its operational impact.
