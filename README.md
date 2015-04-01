# Example of NFS volume

## NFS server part

Define [NFS server pod](nfs-server-pod.yaml) and
[NFS service](nfs-server-service.yaml):

    $ kubectl create -f nfs-server-pod.yaml
    $ kubectl create -f nfs-server-service.yaml

The server exports /mnt/data directory, which contains dummy index.html.
Wait until the pod is running!

TODO: export content of a Google cloud volume.

## NFS client (the real example)

See [WEB server pod](web-pod.yaml), which runs a simple web server serving
data from the NFS. The pod assumes your DNS is set up and the NFS service is
reachable as `nfs-server.default.kube.local`. Edit the yaml file to supply
another name or directly its IP address (use `kubectl get services` to get it).

Finally, define the pod:

    $ kubectl create -f web-pod.yaml

Now the pod serves index.html from the NFS server:

    $ curl http://<the container IP address>/
    Hello World!
