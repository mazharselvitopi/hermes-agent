# Docker Compose

## Dokploy / server (default)

Dokploy runs `docker compose -f ./docker-compose.yml`. Use `docker-compose.yml` in the repo root (not `.yaml`).

```bash
docker compose up -d --build
```

Data is stored in the named volume `hermes-data` (portable on servers; no `~/.hermes` bind).

## Local audio (optional)

- Linux host with PulseAudio (`/run/user/$UID/pulse`).
- Copy `.env.example` to `.env` and set `HERMES_UID` / `HERMES_GID` from `id -u` and `id -g`.

```bash
docker compose -f docker-compose.yml -f docker-compose.audio.yml up -d --build
```

- Gateway API: http://localhost:8642
- Dashboard (when `HERMES_DASHBOARD=1`): http://localhost:9119
- Data: `~/.hermes` → `/opt/data`

## Audio

`Dockerfile.audio` extends `nousresearch/hermes-agent:latest` with ALSA Pulse plugins. `asound.conf` routes ALSA to Pulse inside the container; Pulse connects to the host via the mounted socket and cookie.
