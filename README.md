# Gateway Proxy

A centralized reverse proxy solution using Nginx that manages traffic routing for multiple microservices and applications deployed across different subdomains.

## Overview

This repository contains the centralized Nginx configuration that acts as the main entry point for all services in the ecosystem. It handles SSL termination, subdomain routing, and load balancing for multiple applications running in separate Docker containers.

## Features

- **Centralized SSL Management**: Single point for managing SSL certificates across all subdomains
- **Subdomain Routing**: Intelligent traffic routing based on subdomain patterns
- **Reverse Proxy**: Seamless proxying to backend services without exposing internal ports
- **Docker Integration**: Fully containerized setup with Docker Compose
- **Modular Configuration**: Easy addition of new services through individual configuration files
- **Auto HTTPS Redirect**: Automatic redirection from HTTP to HTTPS for all domains
- **WebSocket Support**: Full support for WebSocket connections and upgrades

## Architecture

The gateway proxy sits at the edge of the infrastructure, receiving all incoming HTTP/HTTPS traffic and routing it to the appropriate backend services based on the requested subdomain. Each application runs in its own isolated Docker network while being accessible through the shared proxy network.

```
Internet → Gateway Proxy → Backend Services
           (This Repo)     (Individual Repos)
```