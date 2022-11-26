# File Transfer Protocol (FTP)

Port 21

````bash
# anonymous connect
$ ftp <ip>
````

````bash
# recursive listing
ftp> ls -R
````

````bash
# download file
ftp> get my_file.txt
````

````bash
# anonymous connect
ftp> wget -m --no-passive ftp://anonymous:anonymous@<ip>
````

````bash
# upload file from current folder
ftp> put upload.txt
````

````bash
# run serviceVersion, commonScripts and Agressive scan
$ sudo nmap -sV -p21 -sC -A <ip>
````
