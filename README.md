# Nexus Repository Manager with Docker Support

This is a template for deploying Nexus Repository Manager behind an NGINX reverse proxy.

## Features

- Web UI accessible via https://localhost:9443
- Nexus Docker registry accessible via docker cli 

```
  docker login localhost:19443
```

## Operations

To create and run the Nginx proxy, Nexus Repository Manager and DockerHub proxy, run:

```
./nexus.sh
```

Subsequent runs can use docker-compose:

```
docker-compose up -d
```

To stop, use docker-compose:

```
docker-compose down
```

## SSL Certificates

The Ngnix docker image build process generates insecure SSL certificates with fake location information and CNAME of localhost. Understand the risks of using these SSL certificates before proceeding. A deployed solution should use a valid CA certificate.
