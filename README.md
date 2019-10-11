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

## Administration

Note: There are a few steps you would need to access and create the docker-registry.

1. Access admin.password file to get the random password at the first start.

2. Create a new docker repository.
![Alt text](img/create_docker_repo.png?raw=true "Create a new Docker repository")

3. Create privilege for the docker repository
![Alt text](img/create_privilege.png?raw=true "Create privilege for Docker repository")

4. Create a role with the privilege or add it to an existing role. Create a user and assign the role to the user.

5. Use this user credentials to access the docker repository through the Docker cli.
