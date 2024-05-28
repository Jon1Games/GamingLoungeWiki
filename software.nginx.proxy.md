---
title: ProxyConf
layout: default
permalink: software/nginx/haubtconf/
parent: Nginx
grand_parent: Software
nav_order: 3
---

# Proxy.conf

```
proxy_set_header Host                   $host;
proxy_set_header X-Real-IP              $remote_addr;
proxy_set_header X-Forwarded-For        $proxy_add_x_forwarded_for;
proxy_set_header X-Forwarded-Host       $host;
proxy_set_header X-Forwarded-Server     $host;
proxy_set_header X-Forwarded-Port       $server_port;
proxy_set_header X-Forwarded-Proto      $scheme;
proxy_set_header Upgrade                $http_upgrade;
proxy_set_header Connection             $connection_upgrade;
```
