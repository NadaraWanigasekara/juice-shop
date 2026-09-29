# System Architecture Documentation

## Overview

OWASP Juice Shop is deployed as a containerised web application using Docker Compose. The architecture separates the reverse proxy, application, database and cache services into individual containers.

## Application Flow

The main request flow is:

Browser → Nginx → Juice Shop → MongoDB / Redis

The browser communicates with the Nginx reverse proxy. Nginx acts as the external entry point and forwards application requests to the Juice Shop container. The Juice Shop application communicates with MongoDB for database operations and Redis for caching or related application services.

## Docker Services

The Docker Compose environment contains the following main services:

- *Nginx (juice-shop-proxy)* – reverse proxy and external entry point.
- *Juice Shop (juice-shop-app)* – main web application.
- *MongoDB (juice-shop-mongo)* – database service.
- *Redis* – supporting cache/service component.

The services communicate through the internal Docker network juice-shop-net.

## Network Exposure

Nginx is the externally exposed service, using ports 80 and 443. The Juice Shop application runs internally on port 3000 and is accessed through the Nginx reverse proxy.

MongoDB and Redis are internal services and are not directly exposed to the host.

## Security Boundaries

The architecture provides separation between the external client and internal application services. The Nginx reverse proxy forms the main boundary between external requests and the internal Docker network.

The application also has separate boundaries between the web application and supporting database/cache services. These boundaries are considered when identifying threats and security controls.

## Containerisation

Docker Compose is used to define and manage the application services, dependencies, networking and persistent storage. This provides a reproducible environment for security testing and DevSecOps activities.
