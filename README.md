Generate Publik key from Private key
./xray x25519 -i "ключ"

Stop - start docker
docker compose -f /opt/xray-vps-setup/docker-compose.yml down && docker compose -f /opt/xray-vps-setup/docker-compose.yml up -d

Run xray commands from docker
UUID: docker exec xray-vps-setup-xray-1 xray uuid
XRAY_PBK+PIK: docker exec xray-vps-setup-xray-1 xray x25519
shortid: openssl rand -hex 8

Check docker containers
docker ps

Xray logs
docker logs -f xray-vps-setup-xray-1

Caddy logs
logs -f xray-vps-setup-caddy-1

DNS block on server for ntc.party
"dns": {
    "hosts": {
      "domain:ntc.party": "130.255.77.28"
    },
    "servers": [
      "1.1.1.1",
      "8.8.8.8"
    ],
    "queryStrategy": "UseIPv4",
    "disableFallback": false,
    "tag": "dns-aux"
  }
