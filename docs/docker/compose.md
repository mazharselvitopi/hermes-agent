# Docker Compose

## Prerequisites

- Linux host with PulseAudio (user session socket under `/run/user/$UID/pulse`).
- Copy `.env.example` to `.env` and set `HERMES_UID` / `HERMES_GID` from `id -u` and `id -g`.

## Run

```bash
docker compose up -d --build
```

- Gateway API: http://localhost:8642
- Dashboard (when `HERMES_DASHBOARD=1`): http://localhost:9119
- Data: `~/.hermes` → `/opt/data`

## Audio

`Dockerfile.audio` extends `nousresearch/hermes-agent:latest` with ALSA Pulse plugins. `asound.conf` routes ALSA to Pulse inside the container; Pulse connects to the host via the mounted socket and cookie.
