# Example of NFS volume

## NFS server part

Define [NFS server pod](nfs-pod.yaml) and [NFS service](nfs-service.yaml):

    $ kubectl create -f nfs-server-pod.yaml
    $ kubectl create -f nfs-server-service.yaml

The server exports /mnt/data directory, which contains dummy index.html.
Wait until the pod is running!

TODO: export content of a Google cloud volume.

## NFS client (the example)
Simple web server, serving data from NFS server 

    $ kubectl create -f web-pod.yaml

Now the pod serves index.html from the NFS server:

    $ curl http://172.17.0.9/
    Hello World!
