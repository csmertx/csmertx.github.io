---
title: 💻 Docker
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-05
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> A neat way to setup a DIY media streaming box

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/VMs/docker_installation.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ VMs \ Docker">
       History 🕵️
    </a>
</div>