# Network Architecture

```text
             +----------------------+
             | Client / Kali Linux  |
             | Authorized Testing   |
             +----------+-----------+
                        |
                        | HTTPS :443
                        v
             +----------------------+
             | WAF / Reverse Proxy  |
             | Nginx                |
             | ModSecurity          |
             | OWASP CRS            |
             | TLS                  |
             +----------+-----------+
                        |
                        | Backend traffic
                        v
             +----------------------+
             | Backend Web Server   |
             | Nginx / Application  |
             +----------------------+
```

## Example network plan

```text
WAF subnet:       10.10.10.0/24
Backend subnet:   10.10.20.0/24
WAF:              10.10.10.10
Backend:          10.10.20.10
Application DNS:  app.example.local
```

## Security boundaries

1. Untrusted clients reach only the WAF application interface.
2. Backend application ports should be restricted to trusted WAF/application networks where practical.
3. Administrative interfaces should be isolated from public application traffic.
4. WAF logs should be protected from unauthorized modification.
5. Production secrets/private keys must stay outside Git.
