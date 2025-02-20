Before you start the task, please read this:

    Please screenshot the command step-by-step
    Describe the process in your final task repository

Requirements

    NGINX/Apache2/Lightspeed on Gateway
    SSL Certbot using Wildcard
    Automatic SSL (Ansible/Cronjob/Script etc.)

Instructions

    All domains are HTTPS
    Create Bash Script for Automatic renewal for Certificates
    Create domains:

[ Monitoring ]

    exporter.<name>.studentdumbways.my.id - Node Exporter
    prom.<name>.studentdumbways.my.id - Prometheus
    monitoring.<name>.studentumbways.my.id - Grafana

[ Docker Registry ]

    registry.<name>.studentdumbways.my.id - Docker Registry

[ Staging ]

    staging.<name>.studentdumbways.my.id - App
    api.staging.<name>.studentdumbways.my.id - Backend API

[ Production ]

    <name>.studentdumbways.my.id - App
    api.<name>.studentdumbways.my.id - Backend API

JAWABAN:

# Buat file docker-compose.yaml untuk nginx

![image](https://github.com/user-attachments/assets/59d1354b-572b-448f-aece-e852265fd2e0)

![image](https://github.com/user-attachments/assets/2eaf0023-cf31-4d2a-85d9-2a65836b2a2b)

# Buat file default.conf untuk konfigurasi reverse proxy

![image](https://github.com/user-attachments/assets/c91c62d1-536d-44ed-915f-f9cdf0eb09cd)


    server {
    listen 80;
    server_name api.staging.studentdumbways.my.id staging.studentdumbways.my.id api.production.studentdumbways.my.id production.studentdumbways.my.id registry.daffa.studentdumbways.my.id exporter1-production.studentdumbways.my.id exporter2-getaway.studentdumbways.my.id exporter3-staging.studentdumbways.my.id exporter4-registry.studentdumbways.my.id exporter5-monitoring.studentdumbways.my.id prom-daffa.studentdumbways.my.id monitoring-daffa.studentdumbways.my.id;
    return 301 https://$host$request_uri;
  }

    server {
    listen 443 ssl;
    server_name api.staging.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/api.staging.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/api.staging.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://8.221.109.28:5000/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name staging.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/staging.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/staging.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://8.221.109.28:3001/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name api.production.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/api.production.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/api.production.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://103.127.139.123:5000/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name production.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/production.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/production.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://103.127.139.123:3000/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name exporter1-production.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/exporter1-production.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exporter1-production.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://103.127.139.123:9100/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name exporter2-getaway.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/exporter2-getaway.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exporter2-getaway.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://103.127.139.212:9100/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name exporter3-staging.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/exporter3-staging.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exporter3-staging.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://8.221.109.28:9100/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name exporter4-registry.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/exporter4-registry.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exporter4-registry.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://47.130.91.115:9100/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }

    server {
    listen 443 ssl;
    server_name exporter5-monitoring.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/exporter5-monitoring.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exporter5-monitoring.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://13.251.143.29:9100/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    }
    
    server {
    listen 443 ssl;
    server_name prom-daffa.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/prom-daffa.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/prom-daffa.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://13.251.143.29:9090/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

server {
    listen 443 ssl;
    server_name monitoring-daffa.studentdumbways.my.id;

    ssl_certificate /etc/letsencrypt/live/monitoring-daffa.studentdumbways.my.id/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/monitoring-daffa.studentdumbways.my.id/privkey.pem;

    location / {
        proxy_pass http://13.251.143.29:3001/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

upstream jenkins {
        keepalive 32; # keepalive connections
        server 103.127.139.123:8080; # jenkins ip and port
    }

    # Required for Jenkins websocket agents
    map $http_upgrade $connection_upgrade {
        default upgrade;
        '' close;
    }

    # HTTP server (untuk mengalihkan ke HTTPS)
    server {
        listen 80;
        server_name jenkins.daffa.studentdumbways.my.id;
        return 301 https://$server_name$request_uri; # Redirect HTTP ke HTTPS
    }

    # HTTPS server
    server {
        listen 443 ssl;
        server_name jenkins.daffa.studentdumbways.my.id;

        ssl_certificate /etc/letsencrypt/live/jenkins.daffa.studentdumbways.my.id/fullchain.pem;
        ssl_certificate_key /etc/letsencrypt/live/jenkins.daffa.studentdumbways.my.id/privkey.pem;

        # Other SSL settings
        ssl_protocols TLSv1.2 TLSv1.3;
        ssl_ciphers 'HIGH:!aNULL:!MD5';
        ssl_prefer_server_ciphers on;

        # this is the jenkins web root directory
        root /var/run/jenkins/war/;

        access_log /var/log/nginx/jenkins.access.log;
        error_log /var/log/nginx/jenkins.error.log;

        ignore_invalid_headers off;

        location ~ "^/static/[0-9a-fA-F]{8}\/(.*)$" {
            rewrite "^/static/[0-9a-fA-F]{8}\/(.*)" /$1 last;
        }

        location /userContent {
            root /var/lib/jenkins/;
            if (!-f $request_filename){
                rewrite (.*) /$1 last;
                break;
            }
            sendfile on;
        }

        location / {
            sendfile off;
            proxy_pass http://103.127.139.123:8080;
            proxy_redirect default;
            proxy_http_version 1.1;

            # Required for Jenkins websocket agents
            proxy_set_header Connection $connection_upgrade;
            proxy_set_header Upgrade $http_upgrade;

            proxy_set_header Host $http_host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
            proxy_max_temp_file_size 0;

            client_max_body_size 10m;
            client_body_buffer_size 128k;

            proxy_connect_timeout 90;
            proxy_send_timeout 90;
            proxy_read_timeout 90;
            proxy_request_buffering off; # Required for HTTP CLI commands
        }
    }


                
    
