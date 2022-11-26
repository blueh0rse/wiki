# Network File System (NFS)

- port 111
- port 2049

````bash
# nmap scripts
$ sudo nmap --script nfs* <ip> -sV -p111,2049
````

````bash
# show available shares
$ showmount -e <ip>

Export list for <ip>:
/mnt/my_share <ip>/24
````

````bash
# how to mount a share

# create tmp dir to store the shares
$ mkdir /tmp/nfs-shares

# mount the share locally
$ mount -t my_share <ip>:/ /tmp/nfs-shares -o nolock

# show tree
$ cd nfs-shares && tree .
.
└── mnt
    └── my_share
        ├── id_rsa
        ├── id_rsa.pub
        └── nfs.share

2 directories, 3 files
````

````bash
# list usernames and group names
$ ls -l mnt/nfs/
````

````bash
# list Contents with UIDs & GUIDs
$ ls -n mnt/nfs/
````

````bash
# unmount the share
$ umount ./nfs-shares
````
