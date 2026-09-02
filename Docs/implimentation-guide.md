# Deployment Guide

Before production changes, back up approved configurations.

```bash
sudo cp -a /etc/nginx /etc/nginx.backup.$(date +%F)
```

Validate backend reachability:

``bash
curl -I http://<BACKEND_IP>
``

Deployment sequence:

1. Nginx
2. ModSecurity
3. OWASP CRS
4. ModSecurity include configuration
5. TLS
6. Reverse proxy
7. DNS
8. Backend access restrictions
9. Logging
10. Validation

Validate:

```bash
sudo nginx -t
sudo systemctl reload nginx
sudo systemctl status nginx --no-pager
```

Use change management and a tested rollback procedure for production.
