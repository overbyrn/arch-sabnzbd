**Application**

[SABnzbd](http://sabnzbd.org/)

**Description**

SABnzbd is an Open Source Binary Newsreader written in Python. SABnzbd makes Usenet as simple and streamlined as possible by automating everything we can. All you have to do is add an .nzb. SABnzbd takes over from there, where it will be automatically downloaded, verified, repaired, extracted and filed away with zero human interaction.

**Build notes**

Latest stable SABnzbd release from Arch Linux AUR.

**Usage**
```
docker run -d \
    -p 8080:8080 \
    -p 8090:8090 \
    --name=<container name> \
    -v <path for media files>:/media \
    -v <path for config files>:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e UMASK=<umask for created files> \
    -e PUID=<uid for user> \
    -e PGID=<gid for user> \
    binhex/arch-sabnzbd
```

Please replace all user variables in the above command defined by <> with the correct values.

**Access application**

`http://<host ip>:8080`

**Example**
```
docker run -d \
    -p 8080:8080 \
    -p 8090:8090 \
    --name=SABnzbd \
    -v /media/movies:/media \
    -v /apps/docker/sabnzbd:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e UMASK=000 \
    -e PUID=0 \
    -e PGID=0 \
    overbyrn/arch-sabnzbd
```

**Notes**

User ID (PUID) and Group ID (PGID) can be found by issuing the following command for the user you want to run the container as:-

```
id <username>
```
