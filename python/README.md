<!--

********************************************************************************

WARNING:

    DO NOT EDIT "python/README.md"

    IT IS AUTO-GENERATED

    (from the other files in "python/" combined with a set of templates)

********************************************************************************

-->

# Supported tags and respective `Dockerfile` links

## Simple Tags


-	[`3.7.0b3-alpine3.7`, `3.7-rc-alpine3.7`, `rc-alpine3.7`, `3.7.0b3-alpine`, `3.7-rc-alpine`, `rc-alpine` (*3.7-rc/alpine3.7/Dockerfile*)](https://github.com/docker-library/python/blob/5a8233e1b0729298bac9c062ffd4cf0d873e83a2/3.7-rc/alpine3.7/Dockerfile)
-	[`3.6.5-alpine3.7`, `3.6-alpine3.7`, `3-alpine3.7`, `alpine3.7` (*3.6/alpine3.7/Dockerfile*)](https://github.com/docker-library/python/blob/5024b32567b3da4bdd9ce6e317c6c84603015999/3.6/alpine3.7/Dockerfile)
-	[`3.6.5-alpine3.6`, `3.6-alpine3.6`, `3-alpine3.6`, `alpine3.6` (*3.6/alpine3.6/Dockerfile*)](https://github.com/docker-library/python/blob/5024b32567b3da4bdd9ce6e317c6c84603015999/3.6/alpine3.6/Dockerfile)
-	[`2.7.14-alpine3.7`, `2.7-alpine3.7`, `2-alpine3.7` (*2.7/alpine3.7/Dockerfile*)](https://github.com/docker-library/python/blob/04c9c2858a82f0558b4dc2e3788e65103b71af3b/2.7/alpine3.7/Dockerfile)
-	[`2.7.14-alpine3.6`, `2.7-alpine3.6`, `2-alpine3.6` (*2.7/alpine3.6/Dockerfile*)](https://github.com/docker-library/python/blob/04c9c2858a82f0558b4dc2e3788e65103b71af3b/2.7/alpine3.6/Dockerfile)

## Shared Tags

-	`3.7.0b3`, `3.7-rc`, `rc`:
-	`3.7.0b3-windowsservercore`, `3.7-rc-windowsservercore`, `rc-windowsservercore`:
-	`3.6.5`, `3.6`, `3`, `latest`:
-	`3.6.5-windowsservercore`, `3.6-windowsservercore`, `3-windowsservercore`, `windowsservercore`:
-	`3.5.5`, `3.5`:
-	`3.4.8`, `3.4`:
-	`2.7.14`, `2.7`, `2`:
-	`2.7.14-windowsservercore`, `2.7-windowsservercore`, `2-windowsservercore`:

[![Build Status](https://doi-janky.infosiftr.net/job/multiarch/job/arm32v6/job/python/badge/icon) (`arm32v6/python` build job)](https://doi-janky.infosiftr.net/job/multiarch/job/arm32v6/job/python/)

# Quick reference

-	**Where to get help**:  
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:  
	[https://github.com/docker-library/python/issues](https://github.com/docker-library/python/issues)

-	**Maintained by**:  
	[the Docker Community](https://github.com/docker-library/python)

-	**Supported architectures**: ([more info](https://github.com/docker-library/official-images#architectures-other-than-amd64))  
	[`amd64`](https://hub.docker.com/r/amd64/python/), [`arm32v5`](https://hub.docker.com/r/arm32v5/python/), [`arm32v6`](https://hub.docker.com/r/arm32v6/python/), [`arm32v7`](https://hub.docker.com/r/arm32v7/python/), [`arm64v8`](https://hub.docker.com/r/arm64v8/python/), [`i386`](https://hub.docker.com/r/i386/python/), [`ppc64le`](https://hub.docker.com/r/ppc64le/python/), [`s390x`](https://hub.docker.com/r/s390x/python/), [`windows-amd64`](https://hub.docker.com/r/winamd64/python/)

-	**Published image artifact details**:  
	[repo-info repo's `repos/python/` directory](https://github.com/docker-library/repo-info/blob/master/repos/python) ([history](https://github.com/docker-library/repo-info/commits/master/repos/python))  
	(image metadata, transfer size, etc)

-	**Image updates**:  
	[official-images PRs with label `library/python`](https://github.com/docker-library/official-images/pulls?q=label%3Alibrary%2Fpython)  
	[official-images repo's `library/python` file](https://github.com/docker-library/official-images/blob/master/library/python) ([history](https://github.com/docker-library/official-images/commits/master/library/python))

-	**Source of this description**:  
	[docs repo's `python/` directory](https://github.com/docker-library/docs/tree/master/python) ([history](https://github.com/docker-library/docs/commits/master/python))

-	**Supported Docker versions**:  
	[the latest release](https://github.com/docker/docker-ce/releases/latest) (down to 1.6 on a best-effort basis)

# What is Python?

Python is an interpreted, interactive, object-oriented, open-source programming language. It incorporates modules, exceptions, dynamic typing, very high level dynamic data types, and classes. Python combines remarkable power with very clear syntax. It has interfaces to many system calls and libraries, as well as to various window systems, and is extensible in C or C++. It is also usable as an extension language for applications that need a programmable interface. Finally, Python is portable: it runs on many Unix variants, on the Mac, and on Windows 2000 and later.

> [wikipedia.org/wiki/Python_(programming_language)](https://en.wikipedia.org/wiki/Python_%28programming_language%29)

![logo](https://raw.githubusercontent.com/docker-library/docs/01c12653951b2fe592c1f93a13b4e289ada0e3a1/python/logo.png)

# How to use this image

## Create a `Dockerfile` in your Python app project

```dockerfile
FROM arm32v6/python:3

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD [ "python", "./your-daemon-or-script.py" ]
```

or (if you need to use Python 2):

```dockerfile
FROM arm32v6/python:2

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD [ "python", "./your-daemon-or-script.py" ]
```

You can then build and run the Docker image:

```console
$ docker build -t my-python-app .
$ docker run -it --rm --name my-running-app my-python-app
```

## Run a single Python script

For many simple, single file projects, you may find it inconvenient to write a complete `Dockerfile`. In such cases, you can run a Python script by using the Python Docker image directly:

```console
$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp arm32v6/python:3 python your-daemon-or-script.py
```

or (again, if you need to use Python 2):

```console
$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp arm32v6/python:2 python your-daemon-or-script.py
```

# Image Variants

The `arm32v6/python` images come in many flavors, each designed for a specific use case.

## `arm32v6/python:<version>`

This is the defacto image. If you are unsure about what your needs are, you probably want to use this one. It is designed to be used both as a throw away container (mount your source code and start the container to start your app), as well as the base to build other images off of. This tag is based off of [`buildpack-deps`](https://registry.hub.docker.com/_/buildpack-deps/). `buildpack-deps` is designed for the average user of docker who has many images on their system. It, by design, has a large number of extremely common Debian packages. This reduces the number of packages that images that derive from it need to install, thus reducing the overall size of all images on your system.

## `arm32v6/python:alpine`

This image is based on the popular [Alpine Linux project](http://alpinelinux.org), available in [the `alpine` official image](https://hub.docker.com/_/alpine). Alpine Linux is much smaller than most distribution base images (~5MB), and thus leads to much slimmer images in general.

This variant is highly recommended when final image size being as small as possible is desired. The main caveat to note is that it does use [musl libc](http://www.musl-libc.org) instead of [glibc and friends](http://www.etalabs.net/compare_libcs.html), so certain software might run into issues depending on the depth of their libc requirements. However, most software doesn't have an issue with this, so this variant is usually a very safe choice. See [this Hacker News comment thread](https://news.ycombinator.com/item?id=10782897) for more discussion of the issues that might arise and some pro/con comparisons of using Alpine-based images.

To minimize image size, it's uncommon for additional related tools (such as `git` or `bash`) to be included in Alpine-based images. Using this image as a base, add the things you need in your own Dockerfile (see the [`alpine` image description](https://hub.docker.com/_/alpine/) for examples of how to install packages if you are unfamiliar).

# License

View license information for [Python 2](https://docs.python.org/2/license.html) and [Python 3](https://docs.python.org/3/license.html).

As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

Some additional license information which was able to be auto-detected might be found in [the `repo-info` repository's `python/` directory](https://github.com/docker-library/repo-info/tree/master/repos/python).

As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.
