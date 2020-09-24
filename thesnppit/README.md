# Image: thesnppit

This image is based on the official Docker image [postgres:9.5](https://hub.docker.com/_/postgres). Installer for [TheSNPpit] is added into the image, but it is not installed as the image's build process because its installation requires the database being running. Once a container instance of this image is started and the database is up and running, a user will need to manually initiate `TheSNPpit`'s installation.

The following is an example of creating a container instance of this image with a `bind` mount to persist PostgreSQL database's data

```
$ docker run --name thesnppit -e POSTGRES_PASSWORD=password -v $PWD/volumes/pg_data:/var/lib/postgresql/data -d agresearch/thesnppit:1.1.4
```

## Install **TheSNPpit**

When the container instance is running, invoke `INSTALL` in `/usr/local/TheSNPpit-1.1.4/bin` from `/usr/local/TheSNPpit-1.1.4` as user `root` (the installer is very particular with the location and user where/whom it is invoked).

```
$ docker exec --user root -it thesnppit bash -c "cd /usr/local/TheSNPpit-1.1.4/; bin/INSTALL
```

The installer will create a user `snpadmin` inside the container and it is the user account to impersonate when interacting with the **TheSNPpit** database via its `snppit` command.

```
$ docker exec --user snpadmin -it thesnppit-dev snppit -v
```
