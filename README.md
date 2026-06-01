# hermes-agent

Hermes Agent via Docker. Dokploy and other tools expect **`docker-compose.yml`** in the repo root.

```bash
# Server / Dokploy
docker compose up -d --build

# Local Linux + PulseAudio (optional)
docker compose -f docker-compose.yml -f docker-compose.audio.yml up -d --build
```

See [docs/docker/compose.md](docs/docker/compose.md).