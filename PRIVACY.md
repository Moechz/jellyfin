# Privacy Policy — Jellyfin for TerraMaster TOS 7

This policy describes how the **Jellyfin** Docker application package
(`jellyfindocker`) handles data when installed on your TerraMaster NAS.

- Package: `jellyfindocker` (TOS 7 App Center, Docker application)
- Upstream software: [Jellyfin](https://jellyfin.org) 10.11.11
- Publisher: Moechz

## 1. Scope

The application runs the official `jellyfin/jellyfin` Docker Hub image as a
non-root container (uid 1000). This policy covers the package and its default
configuration. Plugins you install yourself may have their own behaviour.

## 2. Data stored on your NAS

All application data stays in `/Volume1/DockerAppData/jellyfindocker/`:

| Data | Where | Why |
|---|---|---|
| Library index and metadata (titles, artwork, subtitles) | `config/` | Media library |
| User accounts, password hashes, watch state, favourites | `config/` | Authentication and playback progress |
| Server settings, plugin list, logs | `config/` | Operation and troubleshooting |
| Transcoding cache | `cache/` | Playback performance |

No data from the library is uploaded to the publisher or to TerraMaster.

## 3. Data sent off your NAS

Jellyfin contacts external services only for the features you enable:

- **Metadata providers** — TheMovieDb, TheTVDB, MusicBrainz, OMDb: the title,
  external ID or image URL being looked up is sent to fetch metadata and artwork.
- **Plugin repository** — GitHub-hosted plugin catalog, for plugin listings and updates.
- **Subtitle providers** (if enabled) — the file hash or title is sent to the provider.
- **Notifications / webhooks** (if configured) — sent to the endpoints you configure.
- **Client connections** — Jellyfin clients connect to your NAS directly; traffic
  never passes through the publisher.

The publisher collects no telemetry, analytics or crash reports and operates no
server that receives data from this application.

## 4. Third parties

| Recipient | Data | Purpose |
|---|---|---|
| TheMovieDb / TheTVDB / MusicBrainz / OMDb | Title, external ID, image URL | Metadata and artwork |
| GitHub (plugin catalog) | HTTP request metadata | Plugin discovery and updates |
| Subtitle providers you enable | Title or file hash | Subtitle search |
| Endpoints you configure | Notification payload | Alerts |

No data is sold or shared for advertising.

## 5. Retention

Data is kept while the application is installed and you keep it. Watch history
and metadata can be cleared per user or per library in the Jellyfin settings.
Deleting `/Volume1/DockerAppData/jellyfindocker/` removes everything.

## 6. Your rights

- **Access / portability** — browse or export metadata from the Jellyfin
  database; library files themselves are not copied by the application.
- **Rectification** — edit metadata, users and settings in the UI.
- **Erasure** — delete users, libraries or the whole data directory.
- **Restriction** — disable metadata providers, plugins and notifications.

The publisher never receives your data, so requests are handled locally by you.

## 7. Security measures

- Container runs as uid 1000 (non-root), no privileged mode, no host network,
  no Docker socket access.
- Data directory is writable only by that user.
- The web UI is served over plain HTTP on your LAN; if exposed to the internet,
  place it behind HTTPS and authentication.

## 8. Deletion channel

App Center → uninstall the application **and** remove
`/Volume1/DockerAppData/jellyfindocker/`. There is no server-side copy to delete.

## 9. Changes

Material changes are published in this file and noted in the package changelog
with the version that introduced them.

## 10. Contact

Open an issue at <https://github.com/Moechz/jellyfin/issues>.
