Gogs + Drone
============

Demo on creating CI/CD service using Gogs and Drone via docker-compose

Requirements
------------

- docker
- docker-compose

Installation
------------

For demonstration, we need to create 2 `/etc/hosts` entries pointing to `127.0.0.1` to ensure these duo can communicate to each others both from inside container and from outside world.

```
127.0.0.1 gogs
127.0.0.1 drone-server
```

First, create docker volumes named `gogs, drone, mariadb`.

```sh
docker volume create gogs
docker volume create drone
docker volume create mariadb
```

If you prefer different volume names, make sure you edit `docker-compose.yml` to match your preference.

When things ready, bring up all services using `docker-compose` magic.

```sh
docker-compose up -d
```

Setup Gogs
----------

Now navigate to http://gogs:10080/ gogs will walk you through the installation process. Fill out the form and Gogs will redirect you to login page.

Setup Drone
-----------

When you are done with Gogs, you can now login to drone at http://drone-server:8000/ using your gogs credential, drone will then try to manage your ropositories on your behalf.

Todo
----

- ☐ Detail on what to fill on Gogs installation process.
- ☐ Detail on creating integration on Drone UI.

Author
------

Porawit Poboonma

Credit
------

- Gogs
- Drone
