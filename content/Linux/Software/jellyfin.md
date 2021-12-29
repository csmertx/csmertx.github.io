### Docker
- apti snapd
- sudo snap install docker
- sudo docker pull jellyfin/jellyfin
- mkdir ~/.config/jellyfin
- mkdir ~/.config/jellyfin/config
- mkdir ~/.config/jellyfin/cache
- Server start (give first run 20min-1hr+ to cache)
    - sudo docker run -d \
    - --volume /home/$USER/.config/jellyfin/config:/config \
    - --volume /home/$USER/.config/jellyfin/cache:/cache \
    - --volume /mnt/Storage/Videos:/data/videos \
    - --volume /mnt/Storage/Music:/data/music \
    - --volume /mnt/Storage/Pictures:/data/pictures \
    - --user 1000:1000 \
    - --net=host \
    - --restart=unless-stopped \
    - jellyfin/jellyfin
- Server stop
    - sudo docker ps -aq
    - sudo docker stop [listedcontainer]
- sudov /etc/sudoers (!)
    - add to NOPASSWD: /snap/bin/docker

### Not running after system update(s)?
- $HOME/.scripts/jellyfin_setup.sh

### Restart
- sudo docker ps -aq
- sudo docker restart [container]
