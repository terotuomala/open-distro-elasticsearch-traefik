# Open Distro for Elasticsearch with Traefik
Open Distro for Elasticsearch stack running in Docker with Traefik as Reverse Proxy. Traefik handles traffic to Kibana Web Interface. Elasticsearch persist it's data to Docker volume. Health checks of the Kibana and Elasticsearch services is also included.

### Usage with docker-compose
Create docker network for traefik:
```
docker network create traefik-network
```
Start the environment:
```
docker-compose up
```
Open Kibana Web interface or Traefik Dashboard using Chrome (because it can resolve any *.localhost to the loopback interface): 
```
http://kibana.localhost/
http://kibana.localhost:8080/dashboard
```
Kibana uses initial username `admin` and password `admin`

### Example message
...