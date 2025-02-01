# Unifi contoller with NPM proxy


## Reverse proxy with NPM
### Proxy host
- https://unifi-controller:8443
- Turn on **Websocket Support**
- Turn on **Block Common Exploits**
### Add following adv conf in NPM
```nginx
location /wss/ {
    proxy_pass https://unifi-controller:8443;
    proxy_set_header Host $host;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "Upgrade";
}
```