# home-monitor-docker

This repository contains a docker-compose file to run a basic home monitoring system with a Raspberry Pi or any other device that supports Docker. The system is composed of the following services:

- [blackbox-exporter](https://github.com/prometheus/blackbox_exporter): Exposes an HTTP endpoint with metrics on ICMP probes and DNS lookups.
- [prometheus](https://prometheus.io/): Collects metrics from blackbox-exporter and stores them in a time-series database.
- [grafana](https://grafana.com/): Visualizes the metrics stored in Prometheus.

## Requirements

- Docker
- Docker Compose

## Usage

1. Clone this repository.
2. Change to the repository directory and start the services:
```bash
cd home-monitor-docker
# -d flag runs the services in the background
docker-compose up -d
```
4. Access Grafana at [http://localhost:3000](http://localhost:3000) with the following credentials:
    - Username: `admin`
    - Password: `admin`

## Tips

- If you are new to docker, it would be helpful to install [lazydocker](https://github.com/jesseduffield/lazydocker) so you can inspect the services running in your docker environment.
- `docker-compose down` will stop and remove the services, but will not remove the volumes. If you want to remove the volumes as well, use `docker-compose down -v`.
