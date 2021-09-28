# Argos
Monitoring stack featuring Grafana, Prometheus, Loki, Promtail, and Node Exporter bundled into Docker Compose

## Pre-Requisites
Before you begin, ensure you have the latest version of docker and docker-compose installed on your system.
* Docker: https://docs.docker.com/get-docker/
* Docker-Compose: https://docs.docker.com/compose/install/


---
### Loki Docker Driver
On the host you're dedicating to this stack, and any other machines that are running docker containers you wish to monitor, install the Loki Docker Driver

`docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions`

More info can be found here: https://grafana.com/docs/loki/latest/clients/docker-driver/

---

## Installation

To use this stack, navigate to `/var` clone this repo. If you wish to clone this into a different directory, you will need to modify the `argos.yml` file and update the paths to match your working directory.

`git clone https://github.com/skisec/argos.git` and `cd argos`

Once you are in your inside `/var/argos` run the following to spin up the stack:

`docker-compose -f argos.yml up -d`

You can access the services at the following ports:
* Grafana: `<YOUR IP>:3000`
* Prometheus: `<YOUR IP>:9090`


## Setup
Once you have the stack deployed, you will need to add the Loki and Prometheus datasources in Grafana.
