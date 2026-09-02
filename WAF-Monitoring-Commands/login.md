# WAF Monitoring Commands

## Live traffic

```bash
sudo tail -f /var/log/nginx/access.log
```

## Nginx errors

```bash
sudo tail -f /var/log/nginx/error.log
```

## ModSecurity events

```bash
sudo tail -f /var/log/modsec_audit.log
```

## Search blocked events

```bash
sudo grep -i "Access denied" /var/log/modsec_audit.log
```

## Search XSS events

```bash
sudo grep -i "XSS" /var/log/modsec_audit.log
```

## Search a CRS rule

```bash
sudo grep "941160" /var/log/modsec_audit.log
```

## Service/configuration checks

```bash
sudo systemctl status nginx --no-pager
sudo nginx -t
sudo nginx -T | grep -A20 "proxy_pass"
```

Nginx log rotation commonly creates `access.log.1`, `access.log.2.gz`, etc. Historical compressed logs can be searched with `zgrep`.
