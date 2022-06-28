**Install in manjaro**
https://docs.docker.com/engine/install/linux-postinstall/
```bash
sudo systemctl enable docker.service
sudo systemctl start containerd.service
sudo groupadd docker
sudo usermod -aG docker $USER
```
---
**Docker удаление всех томов(volumes)**
```bash
docker volume prune
```
***

**Получение ip контейнера postgres_postgres для pgadmin4**
```bash
docker network inspect postgres_postgres
```
***

**Generate openapi in docker** 
```bash
docker run --rm \
	-v ${PWD}:/local openapitools/openapi-generator-cli generate \
	-i /local/api/openapi.yaml \
	-g go-echo-server \
	-o /local/gen
```
#openapi
***

**pg_dump из docker postgres**
```bash
docker exec -t your-db-container pg_dumpall -c -U postgres > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql
```
#postgres
***
