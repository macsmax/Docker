# Docker
Playing with Docker. cadvisor is included in the docker-composes below for monitoring purposes.

## tvs - Docker tv services
This is a docker-compose that I crafted to install Plex, Sickrage and all things nice.

Please modify the docker compose file to fit to your needs.

* 192.168.155.20 is a syslogd server
* /data01 and /data02 are storage volumes

## owncloud
Owncloud set of docker containers. nginx-proxy acts as ssl offload.

Please modify the docker compose file to fit to your needs.
* Please configure the virtual_host for owncloud
* 192.168.155.20 is a syslogd server
* /data01 and /data02 are storage volumes
