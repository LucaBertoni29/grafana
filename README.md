# Dashboard Grafana

Setup delle dashboard in Grafana

## Installazione Portainer

```bash
sudo docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```

## Dashboard Pi-Hole

```bash
docker run \                                           
  -e 'PIHOLE_HOSTNAME=IP' \
  -e 'PIHOLE_PASSWORD=password' \
  -e 'PORT=9617' \
  -p 9617:9617 \
  ekofr/pihole-exporter:latest
```

## Dashboard Bitcoin Core

```bash
docker run \
    --name=bitcoin-exporter \
    -p 9332:9332 \
    -e BITCOIN_RPC_HOST=192.168.1.3 \
    -e BITCOIN_RPC_USER=user \
    -e BITCOIN_RPC_PASSWORD=password \
    jvstein/bitcoin-prometheus-exporter:v0.7.0

```
