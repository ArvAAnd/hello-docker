# Flask Redis Counter (Dockerized)

A lightweight web application built with Flask and Redis to demonstrate containerization, multi-container orchestration, and basic state persistence.

## Tech Stack
* Python
* Flask
* Redis
* Docker
* Docker Compose

## Core Functionality
* Hit Counter: Tracks and displays the number of page views by incrementing a key in Redis via `redis_client.incr`.
* Multi-Container Networking: The Flask application communicates with the Redis isolated service instance using Docker's internal DNS resolution (`host='redis'`).
* Environment Configuration: Dynamic port binding managed through environment variables (`APP_PORT`).

## Docker Infrastructure
* Dockerfile: Configures a lightweight Python 3.9 environment, installs dependencies, handles layer caching for `requirements.txt`, and exposes port 5000.
* Docker Compose: Orchestrates two microservices (`web` and `redis`). Implements startup order enforcement using `depends_on` to ensure Redis is available before the web server initializes.

## How to Run
1. Ensure Docker and Docker Compose are installed.
2. Build and start the containers:
```bash
   docker compose up --build
