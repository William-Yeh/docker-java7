Docker-Java7
============

## Summary

Repository name in Docker Hub: **[williamyeh/java7](https://registry.hub.docker.com/u/williamyeh/java7/)**

This repository contains Dockerized [Java](https://www.java.com/) 1.7, published to the public [Docker Hub](https://registry.hub.docker.com/) via **automated build** mechanism.



## Configuration

This docker image contains the following software stack:

- OS: Debian jessie (built from [debian:jessie](https://registry.hub.docker.com/_/debian/)).

- Java: Oracle JDK 1.7.0_65-b17


### Dependencies

- [debian:jessie](https://registry.hub.docker.com/_/debian/).



## Why yet another Java image for Docker?

There has been quite a few Java images for Docker (e.g., [search](https://registry.hub.docker.com/search?q=java) in the Docker Hub), so why reinvent the wheel?

In the beginning I used the [pulse00/java](https://github.com/dubture-dockerfiles/java). It worked well, but left some room for improvement:

- *Base OS image* - It was built from [stackbrew/ubuntu:13.10](https://registry.hub.docker.com/u/stackbrew/ubuntu/), which may not be the smallest one.  On the other hand, [debian:jessie](https://registry.hub.docker.com/_/debian/), as recommended in this [article](http://crosbymichael.com/dockerfile-best-practices-take-2.html), worth a try.

- *Unnecessary dependencies* - It installed, at the very beginning of its Dockerfile, the [software-properties-common](https://packages.debian.org/sid/admin/software-properties-common) package, which in turns installed some Python3 packages.  I prefered to incorporate these stuff only when absolutely needed.

Therefore, I built this Docker image on my own, also as an exercise.



## Installation

   ```
   $ docker pull williamyeh/java7
   ```


## Usage

Used mostly as a base image for other Java-based applications. But if you'd like to use the CLI, here are some examples for you.


#### Run `java`

```
$ docker run --rm williamyeh/java7
```


#### Run `javac`

```
$ docker run -it --rm williamyeh/java7 javac
```


### Dig into container

```
$ docker run -it williamyeh/java7 bash
```

