# python-oso



<!--ts-->
* [python-oso](#python-oso)
   * [Benefits](#benefits)
      * [Multi Architecture Builds](#multi-architecture-builds)
      * [Small Images via Multi Stage Builds](#small-images-via-multi-stage-builds)
      * [No Rate Limits](#no-rate-limits)
      * [Rapid Building of New Versions](#rapid-building-of-new-versions)
      * [Regular Updates](#regular-updates)
   * [How To](#how-to)
      * [Using the Full Image](#using-the-full-image)
      * [Using the Slim Image](#using-the-slim-image)
      * [Copy Just the Packages](#copy-just-the-packages)
   * [Python Versions](#python-versions)
   * [Image Variants](#image-variants)
      * [Full](#full)
      * [Slim](#slim)
   * [Architectures](#architectures)
   * [Sponsorship](#sponsorship)
   * [Tags](#tags)
      * [Older Tags](#older-tags)
<!--te-->

## Benefits

### Multi Architecture Builds

Every tag in this repository supports these architectures:

* linux/amd64
* linux/arm64


### Small Images via Multi Stage Builds

All libraries are compiled in one image before being moved into the final published image. This keeps all of the build tools out of the published container layers.

### No Rate Limits

This project uses the Github Container Registry to store images, which have no rate limiting on pulls (unlike Docker Hub).

### Rapid Building of New Versions

Within 30 minutes of a new release to oso on PyPI builds will kick off for new containers. This means new versions can be used in hours, not days.

### Regular Updates

Containers are rebuilt weekly in order to take on the security patches from upstream containers.

## How To

### Using the Full Image
The Full Images use the base Python Docker images as their parent. These images are based off of Ubuntu and contain a variety of build tools.

To pull the latest full version:

```bash
docker pull ghcr.io/multi-py/python-oso:py3.11-LATEST
```

To include it in the dockerfile instead:

```dockerfile
FROM ghcr.io/multi-py/python-oso:py3.11-LATEST
```

### Using the Slim Image

The Slim Images use the base Python Slim Docker images as their parent. These images are very similar to the Full images, but without the build tools. These images are much smaller than their counter parts but are more difficult to compile wheels on.

To pull the latest slim version:

```bash
docker pull ghcr.io/multi-py/python-oso:py3.11-slim-LATEST
```

To include it in the dockerfile instead:

```dockerfile
FROM ghcr.io/multi-py/python-oso:py3.11-slim-LATEST
```





### Copy Just the Packages
It's also possible to copy just the Python packages themselves. This is particularly useful when you want to use the precompiled libraries from multiple containers.

```dockerfile
FROM python:3.11

COPY --from=ghcr.io/multi-py/python-oso:py3.11-slim-LATEST /usr/local/lib/python3.11/site-packages/* /usr/local/lib/python3.11/site-packages/
COPY --from=ghcr.io/multi-py/python-oso:py3.11-slim-LATEST /opt/oso /opt/oso
```





## Python Versions

This project actively supports these Python versions:

* 3.11
* 3.10
* 3.9
* 3.8
* 3.7


## Image Variants

Like the upstream Python containers themselves a variety of image variants are supported.


### Full

The default container type, and if you're not sure what container to use start here. It has a variety of libraries and build tools installed, making it easy to extend.



### Slim

This container is similar to Full but with far less libraries and tools installed by default. If yo're looking for the tiniest possible image with the most stability this is your best bet.





## Architectures

Every tag in this repository supports these architectures:

* linux/amd64
* linux/arm64


## Sponsorship

If you get use out of these containers please consider sponsoring me using Github!
<center>

[![Github Sponsorship](https://raw.githubusercontent.com/mechPenSketch/mechPenSketch/master/img/github_sponsor_btn.svg)](https://github.com/sponsors/tedivm)

</center>

## Tags
* Recommended Image: `ghcr.io/multi-py/python-oso:py3.11-0.26.4`
* Slim Image: `ghcr.io/multi-py/python-oso:py3.11-slim-0.26.4`

Tags are based on the package version, python version, and the upstream container the container is based on.

| oso Version | Python Version | Full Container | Slim Container |
|-----------------------|----------------|----------------|----------------|
| latest | 3.11 | py3.11-latest | py3.11-slim-latest |
| latest | 3.10 | py3.10-latest | py3.10-slim-latest |
| latest | 3.9 | py3.9-latest | py3.9-slim-latest |
| latest | 3.8 | py3.8-latest | py3.8-slim-latest |
| latest | 3.7 | py3.7-latest | py3.7-slim-latest |
| 0.26.4 | 3.11 | py3.11-0.26.4 | py3.11-slim-0.26.4 |
| 0.26.4 | 3.10 | py3.10-0.26.4 | py3.10-slim-0.26.4 |
| 0.26.4 | 3.9 | py3.9-0.26.4 | py3.9-slim-0.26.4 |
| 0.26.4 | 3.8 | py3.8-0.26.4 | py3.8-slim-0.26.4 |
| 0.26.4 | 3.7 | py3.7-0.26.4 | py3.7-slim-0.26.4 |
| 0.26.3 | 3.11 | py3.11-0.26.3 | py3.11-slim-0.26.3 |
| 0.26.3 | 3.10 | py3.10-0.26.3 | py3.10-slim-0.26.3 |
| 0.26.3 | 3.9 | py3.9-0.26.3 | py3.9-slim-0.26.3 |
| 0.26.3 | 3.8 | py3.8-0.26.3 | py3.8-slim-0.26.3 |
| 0.26.3 | 3.7 | py3.7-0.26.3 | py3.7-slim-0.26.3 |
| 0.26.2 | 3.11 | py3.11-0.26.2 | py3.11-slim-0.26.2 |
| 0.26.2 | 3.10 | py3.10-0.26.2 | py3.10-slim-0.26.2 |
| 0.26.2 | 3.9 | py3.9-0.26.2 | py3.9-slim-0.26.2 |
| 0.26.2 | 3.8 | py3.8-0.26.2 | py3.8-slim-0.26.2 |
| 0.26.2 | 3.7 | py3.7-0.26.2 | py3.7-slim-0.26.2 |
| 0.26.1 | 3.11 | py3.11-0.26.1 | py3.11-slim-0.26.1 |
| 0.26.1 | 3.10 | py3.10-0.26.1 | py3.10-slim-0.26.1 |
| 0.26.1 | 3.9 | py3.9-0.26.1 | py3.9-slim-0.26.1 |
| 0.26.1 | 3.8 | py3.8-0.26.1 | py3.8-slim-0.26.1 |
| 0.26.1 | 3.7 | py3.7-0.26.1 | py3.7-slim-0.26.1 |
| 0.26.0 | 3.11 | py3.11-0.26.0 | py3.11-slim-0.26.0 |
| 0.26.0 | 3.10 | py3.10-0.26.0 | py3.10-slim-0.26.0 |
| 0.26.0 | 3.9 | py3.9-0.26.0 | py3.9-slim-0.26.0 |
| 0.26.0 | 3.8 | py3.8-0.26.0 | py3.8-slim-0.26.0 |
| 0.26.0 | 3.7 | py3.7-0.26.0 | py3.7-slim-0.26.0 |


### Older Tags

Older tags are left for historic purposes but do not receive updates. A full list of tags can be found on the package's [registry page](https://github.com/multi-py/python-oso/pkgs/container/python-oso).

