# Changelog

## 2026-06-01

### Docker Compose

- Merged duplicate `services.hermes` blocks in `docker-compose.yaml` into a single service definition.
- Combined gateway/dashboard ports and resource limits with PulseAudio/ALSA volume mounts and `Dockerfile.audio` build.
- Added `.env.example` with `HERMES_UID` / `HERMES_GID` for Linux host audio passthrough.
