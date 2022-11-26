# Network Mapper (nmap)

````bash
# update nmap db
$ sudo nmap --script-updatedb
````

Scripts are located in `/usr/share/nmap/scripts/` but it’s possible to find them with a command :

````bash
# find all script starting by 'ftp'
$ find / -type f -name ftp* 2>/dev/null | grep scripts
/usr/share/nmap/scripts/ftp-syst.nse
/usr/share/nmap/scripts/ftp-vsftpd-backdoor.nse
/usr/share/nmap/scripts/ftp-vuln-cve2010-4221.nse
````
