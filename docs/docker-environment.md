# Docker Environment Documentation

## Overview

The OWASP Juice Shop environment is deployed using Docker Compose. Docker Compose defines the application services, networking, dependencies, ports and persistent storage required to run the system.

## Docker Services

The environment contains the following services:

| Service | Container | Purpose |
|---|---|---|
| Nginx | juice-shop-proxy | Reverse proxy and external entry point |
| Juice Shop | juice-shop-app | Main web application |
| MongoDB | juice-shop-mongo | Database service |
| Redis | Redis container | Supporting cache/service component |

## Ports

Nginx exposes ports 80 and 443 to the host.

The Juice Shop application runs internally on port 3000. MongoDB and Redis are used as internal services and are not directly exposed to the host.

## Network

The services communicate through the Docker network:

juice-shop-net

This allows the application and supporting services to communicate using their Docker service names.

## Dependencies

The Juice Shop application depends on the supporting Redis and MongoDB services. Health checks and service dependencies are defined through Docker Compose to control the startup order.

## Storage

The Docker Compose configuration uses persistent storage for the Juice Shop application data.

## Security Considerations

Only the Nginx reverse proxy is intended to provide external access. Keeping the application, database and supporting services inside the Docker network reduces unnecessary direct exposure.
