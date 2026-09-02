waf-reverse-proxy.conf.example

# Sanitized Nginx reverse-proxy example.
# Replace placeholders before deployment.

server {
    listen 443 ssl;
    listen [::]:443 ssl;

    server_name app.example.local;

    ssl_certificate     /etc/nginx/ssl/app.example.local.crt;
    ssl_certificate_key /etc/nginx/ssl/app.example.local.key;
    ssl_protocols TLSv1.2 TLSv1.3;

    modsecurity on;
    modsecurity_rules_file /etc/nginx/modsec/main.conf;

    access_log /var/log/nginx/app_access.log;
    error_log  /var/log/nginx/app_error.log;

    location / {
        proxy_pass http://10.10.20.10:80;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;

        proxy_connect_timeout 10s;
        proxy_send_timeout 30s;
        proxy_read_timeout 30s;
    }
}
