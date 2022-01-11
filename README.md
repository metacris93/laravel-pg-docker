# Laravel Demo App with Docker

```
docker-compose up -d --build
docker exec -ti -u <username> <container_name> bash
```
## To Access web server
```
docker exec -ti -u <username> <container_name> bash
```

## To Access database
```
docker exec -ti <container_name> bash
```

## Database
PostgreSQL

## Web Server
Apache