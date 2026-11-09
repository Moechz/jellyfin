# Changelog

All notable user-visible changes to the Jellyfin TOS application package.

## 10.11.11-1 — 2026-11-10

### Added
- First release. Jellyfin (`jellyfin/jellyfin:10.11.11`, Docker Hub official image, unmodified)
  packaged as a TOS 7 Docker application, published on port 8039 and running
  as a non-root user (1000:1000).
- Persistent data is kept under `/Volume1/DockerAppData/jellyfindocker/`.
