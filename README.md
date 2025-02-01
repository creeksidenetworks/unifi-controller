# Unifi contoller with NPM proxy


## Reverse proxy with NPM
### Make sure websocket support is enabled
### Add following adv conf in NPM
```markdown
location /wss/ {
    proxy_pass https://unifi-controller:8443;
    proxy_set_header Host $host;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "Upgrade";
}
```