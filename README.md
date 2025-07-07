# mediamonster

**Eat media files for lunch and watch them as you eat.**

A one-shot Docker-Compose stack that:

* grabs movies, TV and music via qBittorrent  
* automates downloads with Radarr / Sonarr / Lidarr (+ Prowlarr indexer)  
* serves everything instantly through Jellyfin

> No seeding, no manual file moves—finished torrents drop straight into the library and show up in Jellyfin within seconds.

## Stack map

| Service      | Port | Purpose                       |
|--------------|------|-------------------------------|
| Jellyfin     | 8096 | Media server (HTTP)           |
| qBittorrent  | 8080 | Torrent client Web UI         |
| Radarr       | 7878 | Movies automation             |
| Sonarr       | 8989 | TV automation                 |
| Lidarr       | 8686 | Music automation              |
| Prowlarr     | 9696 | Indexer aggregator            |

All containers run as `UID 1000 : GID 1000`.  
Volumes are declared in *docker-compose.yml*—edit paths or user IDs to match your box.

### Spin it up

```bash
docker compose pull
docker compose up -d
