[![TEMPLATE](GRIEFED_GITHUB_REPO_IMAGE)](GRIEFED_GITHUB_REPO)

# TEMPLATE

[![Docker Pulls](https://img.shields.io/docker/pulls/griefed/GRIEFED_DOCKERHUB_REPO?style=for-the-badge&logo=Docker&labelColor=325358&color=c0ffee&logoColor=white)](GRIEFED_DOCKERHUB_REPO)
[![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/griefed/GRIEFED_DOCKERHUB_REPO?label=Image%20size&sort=date&style=for-the-badge&logo=Docker&labelColor=325358&color=c0ffee&logoColor=white)](GRIEFED_DOCKERHUB_REPO)
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/griefed/GRIEFED_DOCKERHUB_REPO?label=Docker%20build&style=for-the-badge&logo=Docker&labelColor=325358&color=c0ffee&logoColor=white)](GRIEFED_DOCKERHUB_REPO)
[![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/griefed/GRIEFED_DOCKERHUB_REPO?label=Docker%20build&style=for-the-badge&logo=Docker&labelColor=325358&color=c0ffee&logoColor=white)](GRIEFED_DOCKERHUB_REPO)
[![GitHub Repo stars](https://img.shields.io/github/stars/Griefed/GRIEFED_GITHUB_REPO?label=GitHub%20Stars&style=for-the-badge&logo=Github&labelColor=325358&color=c0ffee)](GRIEFED_GITHUB_REPO)
[![GitHub forks](https://img.shields.io/github/forks/Griefed/GRIEFED_GITHUB_REPO?label=GitHub%20Forks&style=for-the-badge&logo=Github&labelColor=325358&color=c0ffee)](GRIEFED_GITHUB_REPO)

This is a description.

[![TEMPLATE](GRIEFED_GITHUB_REPO_SCREENSHOT)](ORIGINAL_GITHUB_REPO)

[[_TOC_]]

---

Creates a Container which runs [CREATOR_NAME's](https://github.com/CREATOR_NAME) [CREATOR_REPO](CREATOR_REPO), with [lsiobase/alpine](https://hub.docker.com/r/lsiobase/alpine) as the base image, as seen on EXAMPLE_WEBSITE_IF_EXISTS.

The [lsiobase/alpine](https://hub.docker.com/r/lsiobase/alpine) image is a custom base image built with [Alpine linux](https://alpinelinux.org/) and [S6 overlay](https://github.com/just-containers/s6-overlay).
Using this image allows us to use the same user/group ids in the container as on the host, making file transfers much easier

# Deployment

Tags | Description
-----|------------
`latest` | Using the `latest` tag will pull the latest image for linux/amd64,linux/arm/v7,linux/arm64.
`develop` | The latest image of, if existent, the in-dev version of this container. Use at your own risk!

Using GitHub Workflows, images for this container are multi-arch. Simply pulling `:latest` should retrieve the correct image for your architecture.
Images are available for linux/amd64,linux/arm/v7,linux/arm64.

## pre-built images

```docker-compose.yml
version: "2"
services:
  GRIEFED_DOCKERHUB_REPO:
    container_name: GRIEFED_DOCKERHUB_REPO
    restart: on-failure:3
    image: GRIEFED_DOCKERHUB_REPO
    ports:
      - 8080:PORT
    environment:
      - TZ=Europe/Berlin
      - PUID=1000
      - PGID=1000
    volumes:
      - ./path/to/config:/config
      - ./path/to/data:/data  
```

## cli

```bash
GET_FROM_FLEET
```

# Configuration

| Configuration                                                           | Explanation                                      |
|-------------------------------------------------------------------------|--------------------------------------------------|
| [Restart policy](https://docs.docker.com/compose/compose-file/#restart) | "no", always, on-failure, unless-stopped         |
| TZ                                                                      | Timezone                                         |
| PUID                                                                    | for UserID                                       |
| PGID                                                                    | for GroupID                                      |
| ports                                                                   | The port where the service will be available at. |

## User / Group Identifiers

When using volumes, permissions issues can arise between the host OS and the container. We avoid this issue by allowing you to specify the user `PUID` and group `PGID`.

Ensure any volume directories on the host are owned by the same user you specify and any permissions issues will vanish like magic.

In this instance `PUID=1000` and `PGID=1000`, to find yours use `id user` as below:

```
  $ id username
    uid=1000(dockeruser) gid=1000(dockergroup) groups=1000(dockergroup)
```

# Building the image yourself

Use the [Dockerfile](GRIEFED_GITHUB_REPO/Dockerfile) to build the image yourself, in case you want to make any changes to it

docker-compose.yml:

```docker-compose.yml
version: "2"
services:
  GRIEFED_DOCKERHUB_REPO:
    container_name: GRIEFED_DOCKERHUB_REPO
    restart: on-failure:3
    build: ./GRIEFED_GITHUB_REPO
    ports:
      - 8080:PORT
    environment:
      - TZ=Europe/Berlin
      - PUID=1000
      - PGID=1000
    volumes:
      - ./path/to/config:/config
      - ./path/to/data:/data  
```

1. Clone the repository: `git clone GRIEFED_GITHUB_REPO.git ./GRIEFED_GITHUB_REPO`
1. Prepare docker-compose.yml file as seen above
1. `docker-compose up -d --build GRIEFED_DOCKERHUB_REPO`
1. Visit IP.ADDRESS.OF.HOST:8080
1. ???
1. Profit!
