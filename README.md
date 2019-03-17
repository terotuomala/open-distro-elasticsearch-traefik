# Open Distro for Elasticsearch Traefik
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
Enable Input e.g. GELF HTTP :
```
System -> Inputs -> Select Input -> GELF HTTP -> Launch new input -> Save
```
Send GELF message via HTTP using curl:
```
curl -X POST -H 'Content-Type: application/json' -d '{ "version": "1.1", "host": "example.org", "short_message": "A short message", "level": 5, "_some_info": "foo" }' 'http://localhost:12201/gelf'
```