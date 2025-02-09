---
title: 💻 Docker
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-04-01
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> See also [Jellyfin](/Linux/Software/jellyfin)

## Installation

- ```docker```

- ```sudo systemctl {start,enable} docker.service```

## List Containers

- ```docker images```

- ```sudo docker ps```

## Logs

- ```sudo docker logs containerid```

## Storage Driver

- ```sudov /etc/docker/daemon.json```

    ```
    ++ {
    ++   "storage-driver": "overlay2"
    ++ }
    ```

## Volume examples

- ```docker run -d \```

- ```--volume /dir/media:/media```

## Permissions

- ```sudo usermod -aG docker user```

## Cannot connect to docker daemon error

- ```sudo snap start docker```

- ```sudo systemctl status docker```

- ```sudo systemctl enable docker```

- ```sudo systemctl start docker```

## Purge all the things

- ```sudo docker system prune```

## Docker Compose

- Visit: https://docs.docker.com/compose/install/ 

    > Linux > Install Compose on Linux Systems

- ```sudoc /usr/local/bin/docker-compose```

- ```mkdir ~/.sources/project-name```

- ```cd ~/.sources/project-name```

- ```mv docker-compose.yml ~/.sources/project-name/docker-compose.yml```

- ```docker-compose up```

## Remove Container

- ```docker stop [container_id]```

    > or ```[container_name]```

- ```docker rm [container_id]```
    
    > or ```[container_name]```

## Resources

- [Docker / Docs / Overview](https://docs.docker.com/get-started/overview/)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/docker.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Docker">
       History 🕵️
    </a>
</div>