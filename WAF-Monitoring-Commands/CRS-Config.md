# ModSecurity / OWASP CRS

Typical include order:

```text
modsecurity.conf
      ↓
crs-setup.conf
      ↓
OWASP CRS rules
```

Validate:

```bash
sudo nginx -t
```

OWASP CRS uses anomaly scoring. Rule matches contribute to the inbound anomaly score; the blocking evaluation can return HTTP 403 when the threshold is exceeded.

When tuning false positives, document the rule ID, endpoint, parameter, matched data, business context, and reason for the exception. Prefer narrow exceptions over disabling broad protections.
