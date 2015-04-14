FROM xdrum/openwrt
MAINTAINER Jan Safranek <jsafrane@redhat.com>
EXPOSE 2049/tcp

RUN opkg update && opkg install nfs-kernel-server nfs-kernel-server-utils
ADD run_nfs /usr/bin/run_nfs

ENTRYPOINT ["/usr/local/bin/run_nfs"]