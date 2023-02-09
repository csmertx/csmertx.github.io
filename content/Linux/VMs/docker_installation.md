---
title: Docker
author: csmertx
date: February 5, 2023
weight: -20
---

# Docker: Accelerated, containerized application development

> Or a neat way to setup a DIY media streaming box

## Debian packages

- ```sudo apti docker docker-compose cockpit cockpit-docker```

## Fedora packages

- ```sudo dnf install docker docker-compose cockpit cockpit-docker```

## Add user to docker group (single user LAN server only)

- ```sudo usermod -aG docker $USER```

## Install Nextcloud

- ```sudo docker pull nextcloud```

## IP Address

- add ```IP=192.168.xxx.xx``` to environment

## Link /var/lib/docker to different partition

- remove ```/var/lib/docker```

    > Backup ```/var/lib/docker``` first?

- ```sudo -ln -s /mnt/containers/docker /var/lib/docker```

- ```sudo touch /var/lib/docker/test.txt```

## Configure Cluster (-d for daemonize)

- ```docker-compose -f /mnt/containers/docker-compose/custom_compose.yml up -d```

## Remove Cluster

- ```docker-compose -f /mnt/containers/docker-compose/custom_compose.yml down```

## Resources

- [Docker: Accelerated, Containerized Application Development](https://www.docker.com/)

- [Red Hat - What is Docker?](https://www.redhat.com/en/topics/containers/what-is-docker)
