# Changelog

All notable user-visible changes to the Jellyfin TOS application package.

## 10.11.11-2 — 2026-11-19

### Fixed — App Center listing review remediation
- **C3** Added `PRIVACY.md` (local storage, metadata providers, third-party
  endpoints, retention, user rights, deletion channel) and linked it from Help.
- **C10** Documented the repository layout in `README.md`.
- **F1** Extended the healthcheck start period from 30 s to 180 s and raised
  retries, so a slow first start is no longer reported as a failed installation.

## 10.11.11-1 — 2026-11-10

### Added
- First release. Jellyfin (`jellyfin/jellyfin:10.11.11`, Docker Hub official image, unmodified)
  packaged as a TOS 7 Docker application, published on port 8039 and running
  as a non-root user (1000:1000).
- Persistent data is kept under `/Volume1/DockerAppData/jellyfindocker/`.
