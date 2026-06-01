# Changelog

## 2026-06-01

### Docker Compose

- Merged duplicate `services.hermes` blocks in `docker-compose.yaml` into a single service definition.
- Combined gateway/dashboard ports and resource limits with PulseAudio/ALSA volume mounts and `Dockerfile.audio` build.
- Added `.env.example` with `HERMES_UID` / `HERMES_GID` for Linux host audio passthrough.

### Dokploy fix

- Renamed stack to `docker-compose.yml` (Dokploy expects `./docker-compose.yml`, not `.yaml`).
- Default compose uses named volume `hermes-data` for server/Dokploy deploys.
- PulseAudio/ALSA host mounts moved to optional `docker-compose.audio.yml`.
