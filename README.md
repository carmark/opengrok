# OpenGrok:

opengrok version: [opengrok-1.0](https://github.com/oracle/opengrok/releases/download/1.0/opengrok-1.0.tar.gz)

image base on: [tomcat:8.0](https://registry.hub.docker.com/_/tomcat/)

## Start:

```
sudo docker run -d --rm \
    -v /path/to/source:/src \
    -v /path/to/opengrok_data:/data \
    -p 8888:8080 \
    --name opengrok \
    carmark/opengrok:1.0
```

then, the search engine is available at `http://localhost:8888/source`.

## Reindex
To perform reindex while the container is running, perform the following:

```
sudo docker exec -ti ${CONTAINER_NAME} OpenGrok index /src
```

where the *${CONTAINER_NAME}* is the name/id to this docker image.
