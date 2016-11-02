fluentd-elasticsearch-docker
======================

## Quick start
 - Run `docker-compose up -d` to start the logger and web ui
 - Try to log anything like `docker logs` to `localhost:24224` (See [detail](http://www.fluentd.org/guides/recipes/docker-logging) for logging system for docker through fluentd)
 - Browse `http://localhost:5601` and create new kibana index `logstash-*`
 - Discover your logs

## Build yourself
[Reference](https://github.com/fluent/fluentd-docker-image/blob/master/README.md#how-to-build-your-own-image)
```
docker build -t fluentd-elasticsearch fluentd-elasticsearch
```

## Example `docker-compose.yml`
```
version: '2'
services:
  some-docker:
    image: docker-image-name
    logging:
      driver: fluentd
      options:
        fluentd-address: fluentd-host:24224
        tag: docker.some-docker
```
