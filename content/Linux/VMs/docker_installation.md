---
title: Docker > Installation
weight: -20
---

### Debian packages
=> sudo apti docker docker-compose cockpit cockpit-docker

### Fedora packages
=> sudo dnf install docker docker-compose cockpit cockpit-docker

### Add user to docker group (single user LAN server only)
=> sudo usermod -aG docker $USER

### Install Nextcloud
=> sudo docker pull nextcloud

### ip address
=> add IP=192.168.xxx.xx to environment

### Link /var/lib/docker to different partition
=> remove /var/lib/docker
=> sudo -ln -s /mnt/containers/docker /var/lib/docker
=> sudo touch /var/lib/docker/test.txt

### Configure Cluster (-d for daemonize)
=> docker-compose -f /mnt/containers/docker-compose/custom_compose.yml up -d

### Remove Cluster
=> docker-compose -f /mnt/containers/docker-compose/custom_compose.yml down 
