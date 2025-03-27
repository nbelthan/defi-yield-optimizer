# DeFi Yield Optimizer - Docker Deployment Guide

This document provides instructions for deploying the DeFi Yield Optimizer application using Docker.

## Prerequisites

- Docker installed on your system
- Basic knowledge of Docker commands

## Building the Docker Image

1. Navigate to the project directory:
   ```bash
   cd /path/to/yield-optimizer
   ```

2. Build the Docker image:
   ```bash
   docker build -t yield-optimizer:latest .
   ```

## Running the Container

Run the container with the following command:

```bash
docker run -d -p 80:80 --name yield-optimizer yield-optimizer:latest
```

This will:
- Run the container in detached mode (`-d`)
- Map port 80 of the host to port 80 of the container (`-p 80:80`)
- Name the container "yield-optimizer" (`--name yield-optimizer`)

## Accessing the Application

Once the container is running, you can access the application at:

```
http://localhost
```

If you're running Docker on a remote server, replace "localhost" with the server's IP address or domain name.

## Environment Variables

The application can be configured using the following environment variables:

- `VITE_DEEPSEEK_API_KEY`: Your DeepSeek API key for LLM integration
- `VITE_API_BASE_URL`: Base URL for the DefiLlama API (defaults to "https://api.llama.fi")

Example of running with environment variables:

```bash
docker run -d -p 80:80 \
  -e VITE_DEEPSEEK_API_KEY=your-api-key \
  -e VITE_API_BASE_URL=https://api.llama.fi \
  --name yield-optimizer yield-optimizer:latest
```

## Docker Compose (Optional)

For easier deployment, you can use Docker Compose. Create a `docker-compose.yml` file:

```yaml
version: '3'
services:
  yield-optimizer:
    build: .
    ports:
      - "80:80"
    environment:
      - VITE_DEEPSEEK_API_KEY=your-api-key
      - VITE_API_BASE_URL=https://api.llama.fi
    restart: unless-stopped
```

Then run:

```bash
docker-compose up -d
```

## Troubleshooting

If you encounter issues:

1. Check container logs:
   ```bash
   docker logs yield-optimizer
   ```

2. Verify the container is running:
   ```bash
   docker ps
   ```

3. If needed, restart the container:
   ```bash
   docker restart yield-optimizer
   ```
