# Docker Setup

## Purpose

This container provides a reproducible CLI environment for the AI utilization system.

Included targets:

- Node.js
- Python
- Git
- `gcloud`
- `gws`
- Gemini CLI

## Build And Run

From the repository root:

```bash
docker compose -f docker/docker-compose.yml up --build -d
docker exec -it ai-os bash
```

## Inside The Container

Run the required authentication and setup steps:

```bash
gcloud init
gws auth setup
```

Then verify the tools you need:

```bash
gcloud --version
gws --help
gemini --help
python3 --version
node --version
```

## Notes

- The repository root is mounted into `/workspace`.
- This image is intentionally minimal.
- You can extend it later if you need more tooling.
