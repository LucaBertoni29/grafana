# Dashboard Grafana

Setup delle dashboard in Grafana

## Installazione Portainer

```bash
sudo docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```
## Installazione Grafana

```bash
docker run -d -p 3000:3000 grafana/grafana-enterprise
```

## Installazione Prometheus

```bash
docker run \                                 
     -p 9090:9090 \
     -v /home/user/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
     prom/prometheus
```

## Installazione Dashboard Bitcoin

```bash
docker run \
    --name=bitcoin-exporter \
    -p 9332:9332 \
    -e BITCOIN_RPC_HOST=IP \
    -e BITCOIN_RPC_USER=user \
    -e BITCOIN_RPC_PASSWORD=password \
    jvstein/bitcoin-prometheus-exporter:v0.7.0

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

