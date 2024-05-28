---
title: http
layout: default
permalink: software/nginx/http/
parent: Nginx
grand_parent: Software
nav_order: 2
---

# Configuration von Verbindungen und Virtualisierung

Jeder Code-Block ist eine Webseite.<br>
server_name ist die Domain, und " _ " sind alle verbindungen die nicht von einer vorhandenen Configuration genutz werden.

## Innerhalb des Servers
```
server {
  listen 443;
  listen [::]:443 ssl;
  server_name wiki.gaminglounge.me
  
  include SSL_CERT_PATH;

  location / {
    root /root/GamingLoungeWiki/_site/;
    index index.html;
    include proxy.conf
  }
}
```

## Weiterleitung
```
server {
  listen 443;
  listen [::]:443 ssl;
  server_name youtube.gaminglounge.me
  
  include SSL_CERT_PATH;

  location / {
    prox_pass https://www.youtube.com/@GamingLoungeMC;
    include proxy.conf
  }
}
```

## Weiterleitung von http zu https.
```
server {
  listen 80 default_server;
  isten [::]:80 default_server;
  server_name _;

  return 301 https://$host$request_uri;
}
```
