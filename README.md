Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

Find out the ip address of the attackers system

### OUTPUT:
<img width="588" height="312" alt="image" src="https://github.com/user-attachments/assets/8bf06f12-ed8b-4089-9dd1-31559f4f6077" />


Invoke msfconsole:
### OUTPUT:
<img width="401" height="301" alt="image" src="https://github.com/user-attachments/assets/de9bf72a-1afa-4c66-8606-25ebdae69799" />


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

### OUTPUT:
<img width="777" height="460" alt="image" src="https://github.com/user-attachments/assets/4c29c8f4-663f-4355-b64d-479730df9027" />


Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

### OUTPUT:
<img width="782" height="316" alt="image" src="https://github.com/user-attachments/assets/0a1e417e-8b7b-48ea-93b5-389d934f5c15" />



step4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

### OUTPUT:


Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

### OUTPUT:
<img width="787" height="275" alt="image" src="https://github.com/user-attachments/assets/6bdbbbb8-05ac-40b5-ae7e-c598cc8da04f" />



Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

### OUTPUT:
<img width="780" height="166" alt="image" src="https://github.com/user-attachments/assets/0a873c76-e3e3-44d3-8acc-77290ba57fdb" />



The info command provides information regarding a module or platform,

### OUTPUT:
<img width="753" height="552" alt="image" src="https://github.com/user-attachments/assets/e4b53cf4-05f9-4212-81a7-c0e342a69f80" />


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

### OUTPUT:
<img width="781" height="332" alt="271525953-bd8b69cc-127b-4cdb-a901-0ec46bc2a537" src="https://github.com/user-attachments/assets/a2906040-674a-40db-b59f-8615bbb08186" />


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

### OUTPUT:
<img width="756" height="452" alt="image" src="https://github.com/user-attachments/assets/ca64f801-0c6a-448e-8b8e-33c72d0db2b6" />


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

### OUTPUT:
<img width="782" height="322" alt="image" src="https://github.com/user-attachments/assets/597e5b59-eabf-477b-b59b-5cdce6855c28" />

Use the set rhosts command to set the parameter and run the module, as follows:

### OUTPUT:
<img width="783" height="423" alt="image" src="https://github.com/user-attachments/assets/dae8467d-232b-4699-9657-6b1d041f78d2" />


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

### OUTPUT:
<img width="783" height="227" alt="image" src="https://github.com/user-attachments/assets/67bf62b1-1ad4-4153-b0dc-96c0d770f0db" />


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

### OUTPUT:
<img width="781" height="373" alt="image" src="https://github.com/user-attachments/assets/4edf5d70-084d-44ff-bc6a-d7afed95a203" />


RESULT:
The Metasploit framework for reconnaissance is examined successfully
