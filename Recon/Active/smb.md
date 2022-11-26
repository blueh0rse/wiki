# Server Message Block (SMB)

Tools :

- smbclient
- rpcclient
- smbmap
- CrackMapExec

## smbclient

````bash
# list all shares in anonymous connection
$ smbclient -N -L //<ip>
````

````bash
# list all shares in anonymous connection
$ smbclient -N -L //<ip>
````

````bash
# list all shares in anonymous connection
$ smbclient -N -L //<ip>
````

````bash
# execute commands in your machine
smb: \> !ls
my_file.txt
````

## rpcclient

````bash
# connect to server using rpcclient
rpcclient -U "" <ip>
````

````bash
# rpcclient commands
srvinfo 	                # Server information.
enumdomains 	            # Enumerate all domains that are deployed in the network.
querydominfo 	            # Provides domain, server, and user information of deployed domains.
netshareenumall             # Enumerates all available shares.
netsharegetinfo <share>     # Provides information about a specific share.
enumdomusers 	            # Enumerates all domain users.
queryuser <RID> 	        # Provides information about a specific user.
````

````bash
# query all users
rpcclient $> enumdomusers

user:[mrb3n] rid:[0x3e8]
user:[cry0l1t3] rid:[0x3e9]
````

````bash
# get details of one user
rpcclient $> queryuser 0x3e9
````

````bash
# bruteforce users RIDs
$ for i in $(seq 500 1100);do rpcclient -N -U "" 10.129.14.128 -c "queryuser 0x$(printf '%x\n' $i)" | grep "User Name\|user_rid\|group_rid" && echo "";done

        User Name :     sambauser
        user_rid :      0x1f5
        group_rid:      0x201
````
