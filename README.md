# Description of homelab-docker-machine

This is the docker-compose repo of most apps that I`m running at home now.

## SETUP

- Raspberry pi 4 8gb ram with Ubuntu 20.04
- Storage:
  - 4 external hdds 1tb, all mounted in /mnt
  - Remote old NAS with 16tb storage, also mounted in /mnt

## What apps are included in this stack?

The apps I use in this docker-compose files.

- Traefik - Reverse Proxy.
- Authelia - Private Forward Authentication.
- Watchtower - Automatic Docker Container Updates.
- Portainer - Container Management.
- Heimdall - Unified Frontend.
- Tautulli - Plex statistics and monitoring.
- Jackett - Torrent proxy.
- qBittorrent - Torrent downloader.
- Radarr - Movie management.
- Sonarr - TV Shows management.
- Bazarr - Subtitle Management.
- Plex - Media Server.
- <s>Home Assistant Core - Home Automation.</s>
  - Moved to a dedicated Raspberry pi, check: [aarantes23/home-assistant-config](https://github.com/aarantes23/home-assistant-config)
- TasmoAdim - 
- OpenSpeedTest - 
- MariaDB - MySQL Database.
- phpMyAdmin - Database management.
- Grafana - Graphical data visualization.
- Prometheus - 

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
- Configure some extras settings in the docker-compos, deppending the application
- run `docker-compose up`