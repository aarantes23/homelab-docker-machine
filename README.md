# Description of homelab-docker-machine

This is the docker-compose repo of most apps that I`m running at home now.

## SETUP

- Raspberry pi 4 8gb ram with Ubuntu 20.04
- Storage:
  - 4 external hdds 1tb, all mounted in /mnt
  - Remote old NAS with 16tb storage, also mounted in /mnt

## What apps are included in this stack?

The apps I use in this docker-compose files.

- [Traefik](https://github.com/traefik/traefik) - Reverse Proxy.
- [Authelia](https://github.com/authelia/authelia) - Private Forward Authentication.
- [Watchtower](https://github.com/containrrr/watchtower) - Automatic Docker Container Updates.
- [Portainer](https://github.com/portainer/portainer) - Container Management.
- [Heimdall](https://github.com/linuxserver/Heimdall) - Unified Frontend.
- [Tautulli](https://github.com/linuxserver/docker-tautulli) - Plex statistics and monitoring.
- [Jackett](https://github.com/linuxserver/docker-jackett) - Torrent proxy.
- [qBittorrent](https://github.com/linuxserver/docker-qbittorrent) - Torrent downloader.
- [Radarr](https://github.com/linuxserver/docker-radarr) - Movie management.
- [Sonarr](https://github.com/linuxserver/docker-sonarr) - TV Shows management.
- [Bazarr](https://github.com/linuxserver/docker-bazarr) - Subtitle Management.
- [Plex](https://github.com/linuxserver/docker-plex) - Media Server.
- <s>Home Assistant Core - Home Automation.</s>
  - Moved to a dedicated Raspberry pi, check: [aarantes23/home-assistant-config](https://github.com/aarantes23/home-assistant-config)
- [TasmoAdim](https://github.com/reloxx13/TasmoAdmin) - Admin Website for Devices flashed with Tasmota.
- [OpenSpeedTest](https://hub.docker.com/r/openspeedtest/latest) - HTML5 Internet Speed Test
- [MariaDB](https://github.com/linuxserver/docker-mariadb) - MySQL Database.
- [phpMyAdmin](https://github.com/phpmyadmin/docker) - Database management.
- [Grafana](https://github.com/grafana/grafana) - Graphical data visualization.
- [Prometheus](https://github.com/prometheus/prometheus) - Systems and service monitoring system.

# Usage

## Instructions

- First do the initial config of the server, like:
  - create new user and enable `ssh` access.
  - mount and add all local and remote drives to `/etc/fstab` with the mount point to `/mnt/<hdd-number>`.
  - (optional) share the mounted drives in `samba`.
  - install docker.
  - install docker-compose.
- Clone the repo.
- Configure environmental variables (`.env` file)
  - edit variables in `.env` file.
  - all variables (ie. `${XXX}`) in docker-compose.yml come from `.env` file <b>stored in the same place as `docker-compose.yml`.</b>
- Configure some extras settings in the docker-compos and inside the apps.
- run `docker-compose up`