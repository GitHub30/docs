<!--

********************************************************************************

WARNING:

    DO NOT EDIT "openjdk/README.md"

    IT IS AUTO-GENERATED

    (from the other files in "openjdk/" combined with a set of templates)

********************************************************************************

-->

# Supported tags and respective `Dockerfile` links

## Simple Tags


-	[`8u151-jre-alpine3.7`, `8-jre-alpine3.7`, `jre-alpine3.7`, `8u151-jre-alpine`, `8-jre-alpine`, `jre-alpine` (*8-jre/alpine/Dockerfile*)](https://github.com/docker-library/openjdk/blob/2598f7123fce9ea870e67f8f9df745b2b49866c0/8-jre/alpine/Dockerfile)
-	[`8u151-jdk-alpine3.7`, `8u151-alpine3.7`, `8-jdk-alpine3.7`, `8-alpine3.7`, `jdk-alpine3.7`, `alpine3.7`, `8u151-jdk-alpine`, `8u151-alpine`, `8-jdk-alpine`, `8-alpine`, `jdk-alpine`, `alpine` (*8-jdk/alpine/Dockerfile*)](https://github.com/docker-library/openjdk/blob/2598f7123fce9ea870e67f8f9df745b2b49866c0/8-jdk/alpine/Dockerfile)
-	[`7u151-jre-alpine3.7`, `7-jre-alpine3.7`, `7u151-jre-alpine`, `7-jre-alpine` (*7-jre/alpine/Dockerfile*)](https://github.com/docker-library/openjdk/blob/17d0f9f3411d82622c762163d85cc4a6ba69af95/7-jre/alpine/Dockerfile)
-	[`7u151-jdk-alpine3.7`, `7u151-alpine3.7`, `7-jdk-alpine3.7`, `7-alpine3.7`, `7u151-jdk-alpine`, `7u151-alpine`, `7-jdk-alpine`, `7-alpine` (*7-jdk/alpine/Dockerfile*)](https://github.com/docker-library/openjdk/blob/17d0f9f3411d82622c762163d85cc4a6ba69af95/7-jdk/alpine/Dockerfile)

## Shared Tags

-	`9.0.4-jdk-windowsservercore`, `9.0.4-windowsservercore`, `9.0-jdk-windowsservercore`, `9.0-windowsservercore`, `9-jdk-windowsservercore`, `9-windowsservercore`:
-	`9.0.4-jdk-nanoserver`, `9.0.4-nanoserver`, `9.0-jdk-nanoserver`, `9.0-nanoserver`, `9-jdk-nanoserver`, `9-nanoserver`:
-	`8u161-jdk-windowsservercore`, `8u161-windowsservercore`, `8-jdk-windowsservercore`, `8-windowsservercore`, `jdk-windowsservercore`, `windowsservercore`:
-	`8u161-jdk-nanoserver`, `8u161-nanoserver`, `8-jdk-nanoserver`, `8-nanoserver`, `jdk-nanoserver`, `nanoserver`:

[![Build Status](https://doi-janky.infosiftr.net/job/multiarch/job/arm32v6/job/openjdk/badge/icon) (`arm32v6/openjdk` build job)](https://doi-janky.infosiftr.net/job/multiarch/job/arm32v6/job/openjdk/)

# Quick reference

-	**Where to get help**:  
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:  
	[https://github.com/docker-library/openjdk/issues](https://github.com/docker-library/openjdk/issues)

-	**Maintained by**:  
	[the Docker Community](https://github.com/docker-library/openjdk)

-	**Supported architectures**: ([more info](https://github.com/docker-library/official-images#architectures-other-than-amd64))  
	[`amd64`](https://hub.docker.com/r/amd64/openjdk/), [`arm32v5`](https://hub.docker.com/r/arm32v5/openjdk/), [`arm32v6`](https://hub.docker.com/r/arm32v6/openjdk/), [`arm32v7`](https://hub.docker.com/r/arm32v7/openjdk/), [`arm64v8`](https://hub.docker.com/r/arm64v8/openjdk/), [`i386`](https://hub.docker.com/r/i386/openjdk/), [`ppc64le`](https://hub.docker.com/r/ppc64le/openjdk/), [`s390x`](https://hub.docker.com/r/s390x/openjdk/), [`windows-amd64`](https://hub.docker.com/r/winamd64/openjdk/)

-	**Published image artifact details**:  
	[repo-info repo's `repos/openjdk/` directory](https://github.com/docker-library/repo-info/blob/master/repos/openjdk) ([history](https://github.com/docker-library/repo-info/commits/master/repos/openjdk))  
	(image metadata, transfer size, etc)

-	**Image updates**:  
	[official-images PRs with label `library/openjdk`](https://github.com/docker-library/official-images/pulls?q=label%3Alibrary%2Fopenjdk)  
	[official-images repo's `library/openjdk` file](https://github.com/docker-library/official-images/blob/master/library/openjdk) ([history](https://github.com/docker-library/official-images/commits/master/library/openjdk))

-	**Source of this description**:  
	[docs repo's `openjdk/` directory](https://github.com/docker-library/docs/tree/master/openjdk) ([history](https://github.com/docker-library/docs/commits/master/openjdk))

-	**Supported Docker versions**:  
	[the latest release](https://github.com/docker/docker-ce/releases/latest) (down to 1.6 on a best-effort basis)

# What is OpenJDK?

OpenJDK (Open Java Development Kit) is a free and open source implementation of the Java Platform, Standard Edition (Java SE). OpenJDK is the official reference implementation of Java SE since version 7.

> [wikipedia.org/wiki/OpenJDK](http://en.wikipedia.org/wiki/OpenJDK)

Java is a registered trademark of Oracle and/or its affiliates.

![logo](https://raw.githubusercontent.com/docker-library/docs/a3439b66b7980d1811f6b3835a3c541747172970/openjdk/logo.png)

# How to use this image

## Start a Java instance in your app

The most straightforward way to use this image is to use a Java container as both the build and runtime environment. In your `Dockerfile`, writing something along the lines of the following will compile and run your project:

```dockerfile
FROM arm32v6/openjdk:7
COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
RUN javac Main.java
CMD ["java", "Main"]
```

You can then run and build the Docker image:

```console
$ docker build -t my-java-app .
$ docker run -it --rm --name my-running-app my-java-app
```

## Compile your app inside the Docker container

There may be occasions where it is not appropriate to run your app inside a container. To compile, but not run your app inside the Docker instance, you can write something like:

```console
$ docker run --rm -v "$PWD":/usr/src/myapp -w /usr/src/myapp arm32v6/openjdk:7 javac Main.java
```

This will add your current directory as a volume to the container, set the working directory to the volume, and run the command `javac Main.java` which will tell Java to compile the code in `Main.java` and output the Java class file to `Main.class`.

## Make JVM respect CPU and RAM limits

On startup JVM tries to detect the number of available CPU cores and the amount of RAM to adjust its internal parameters (like the number of garbage collector threads to spawn) accordingly. When container is run with limited CPU/RAM, standard system API, used by JVM for probing, will return host-wide values. This can cause excessive CPU usage and memory allocation errors with older versions of JVM.

Inside Linux containers, recent versions of OpenJDK 8 can correctly detect container-limited number of CPU cores by default. To enable the detection of container-limited amount of RAM the following options can be used:

```console
$ java -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap ...
```

Inside Windows Server (non-Hyper-V) containers, limit for number of available CPU cores does not work (is ignored by Host Compute Service). To set such limit manually, JVM can be started the following way:

```console
$ start /b /wait /affinity 0x3 path/to/java.exe ...
```

In this example CPU affinity hex mask `0x3` will limit JVM to 2 CPU cores.

RAM limit is supported by Windows Server containers, but currently JVM cannot detect it. To prevent excessive memory allocations, `-XX:MaxRAM=...` option must be specified with the value that is not bigger than a containers RAM limit.

# Image Variants

The `arm32v6/openjdk` images come in many flavors, each designed for a specific use case.

## `arm32v6/openjdk:<version>`

This is the defacto image. If you are unsure about what your needs are, you probably want to use this one. It is designed to be used both as a throw away container (mount your source code and start the container to start your app), as well as the base to build other images off of.

## `arm32v6/openjdk:alpine`

This image is based on the popular [Alpine Linux project](http://alpinelinux.org), available in [the `alpine` official image](https://hub.docker.com/_/alpine). Alpine Linux is much smaller than most distribution base images (~5MB), and thus leads to much slimmer images in general.

This variant is highly recommended when final image size being as small as possible is desired. The main caveat to note is that it does use [musl libc](http://www.musl-libc.org) instead of [glibc and friends](http://www.etalabs.net/compare_libcs.html), so certain software might run into issues depending on the depth of their libc requirements. However, most software doesn't have an issue with this, so this variant is usually a very safe choice. See [this Hacker News comment thread](https://news.ycombinator.com/item?id=10782897) for more discussion of the issues that might arise and some pro/con comparisons of using Alpine-based images.

To minimize image size, it's uncommon for additional related tools (such as `git` or `bash`) to be included in Alpine-based images. Using this image as a base, add the things you need in your own Dockerfile (see the [`alpine` image description](https://hub.docker.com/_/alpine/) for examples of how to install packages if you are unfamiliar).

# License

View [license information](http://openjdk.java.net/legal/gplv2+ce.html) for the software contained in this image.

As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

Some additional license information which was able to be auto-detected might be found in [the `repo-info` repository's `openjdk/` directory](https://github.com/docker-library/repo-info/tree/master/repos/openjdk).

As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.
