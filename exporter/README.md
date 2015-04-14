# NFS-exporter container

Inspired by https://github.com/cpuguy83/docker-nfs-server. Rewritten for
OpenWRT to reduce its size.

Available in dockerhub as
[jsafrane/nfsexporter](https://registry.hub.docker.com/u/jsafrane/nfsexporter/).

Usage::

    docker run -d --name nfs --privileged jsafrane/nfsexporter /path/to/share /path/to/share2 ...
