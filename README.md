# FastAPI Continuous Delivery with GitHub Actions

## Overview
This project demonstrates Continuous Delivery by automating the deployment of a Dockerized FastAPI application using GitHub Actions.

## Setup and Installation

### 1. Run Locally
Install dependencies:

```bash
pip install -r requirements.txt
```

Run the server:

```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

### 2. Run with Docker
Build the Docker image:

```bash
docker build -t fastapi-app .
```

Run the container:

```bash
docker run -p 8000:8000 fastapi-app
```

### 3. Deploy with GitHub Actions
The repository contains a GitHub Actions workflow that:
- Builds the Docker image
- Pushes it to Docker Hub

### 4. Pull and Run from Docker Hub

```bash
docker run -p 8000:8000 your-username/fastapi-app:latest
```

## GitHub Actions Workflow
The workflow (`.github/workflows/DockerBuild.yml`) triggers on every push event. It:
- Logs into Docker Hub using secrets.
- Builds the Docker image.
- Pushes the image to Docker Hub.

## Setting Up Docker Hub Credentials in GitHub Actions
1. Generate a Docker Hub Access Token (Docker Hub).
2. Add secrets in GitHub repository:
   - `DOCKER_USERNAME`: Your Docker Hub username
   - `DOCKERTOKEN`: Docker Hub access token.

## Links
- **GitHub Repo**: https://github.com/bhatiasuhani/Devops_githubactions
- **Docker Hub Image**: https://hub.docker.com/u/suhanibhatia23
