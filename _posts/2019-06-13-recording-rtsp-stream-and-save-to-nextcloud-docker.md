---
layout: post
title: "Recording rtsp stream and save to Nextcloud Docker"
category: sysadmin
---

Assuming you have already setup Nextcloud Docker

Using linuxserver/nextcloud https://hub.docker.com/r/linuxserver/nextcloud/

I'm using my current directory, you can use it as an example

Nextcloud Docker volumes are

Host/volume and Path in container

/home/kbeflo/nextcloud/data -- /data
nextcloud_config -- /config

My /home/kbeflo/nextcloud/data is currently mounted on a separate hard drive

fstab entry

    UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx /home/kbeflo/nextcloud/data ext4 defaults 0 1

Now lets create a cron job on our server

    crontab -e

Using ffmpeg to record the output of our cctv camera to my nextcloud user directory

This will make ffmpeg run every hour, on office hours from 8 AM to 5 PM every day

    0 8-17 * * * ffmpeg -i rtsp://192.168.X.X:554/onvif1 -vcodec copy -r 10 -t 3600 -y /home/kbeflo/nextcloud/data/kbeflo/files/cctv/$(date +\%Y\%m\%d\%H).mp4

We will now configure our Nextcloud container to look for the new videos so that they could be viewed on your Nextcloud account

Enter your Nextcloud container shell

    docker exec -it nextcloud /bin/bash

Create cron job on the container that will scan for new files on username kbeflo every hour

    0 * * * * s6-setuidgid abc php7 /config/www/nextcloud/occ files:scan kbeflo

Additional configuration would include a cron job to clean up recordings every n days

    0 0 * * 0 find /home/kbeflo/nextcloud/data/kbeflo/files/cctv -mtime +n -type f -delete

TAGS:sysadmin
