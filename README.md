# Ex.No-05-Metasploit-for-reconnaissance
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

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system



## OUTPUT:
![image](https://github.com/user-attachments/assets/cb8362a2-1d28-411f-973d-87b56b53aac2)

Invoke msfconsole:




## OUTPUT:

![image](https://github.com/user-attachments/assets/14ef563d-22ae-4186-8962-ff2968134c7a)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/user-attachments/assets/13dcd1b1-c425-4d63-8f5d-9d0c0c245dd5)
Port Scanning:

Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).

msf > nmap -sT 192.168.1810/24 -p1-1000

![image](https://github.com/user-attachments/assets/022a40a9-9482-4750-88d5-77457e4567ab)
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.

msf > db_nmap 192.168.181.0/24

![image](https://github.com/user-attachments/assets/127131d5-f865-4e26-abf2-fb777d79fed9)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to

Metasploit's auxiliary modules and list all the scanner modules.

cd /usr/share /metasploit-framework/modules/auxiliary

kali > ls -l
![image](https://github.com/user-attachments/assets/0b28c556-2c6a-4411-b3aa-a6da7fbbc06c)

Search is a powerful command in Metasploit that you can use to find what you want to locate.

msf >search name:Microsoft type:exploit

![image](https://github.com/user-attachments/assets/3567479e-d9db-4927-924a-4e3883af52f5)
search type:auxiliary mysql

![image](https://github.com/user-attachments/assets/d1f4172b-a35e-46e5-8611-e97eac22476d)

search type:auxiliary mysql

![image](https://github.com/user-attachments/assets/a7f3be0d-d6f2-4ef5-901f-3f00b22cac01)

use 11

![image](https://github.com/user-attachments/assets/8ded7df5-4ed0-4e1c-af9a-928f3fe70c8b)

set RHOSTS

![image](https://github.com/user-attachments/assets/8c301971-9d1e-4ecc-96cb-19c60f7b6e95)

![image](https://github.com/user-attachments/assets/4dc85d1b-6e19-4126-bf4b-f6ddc9314bed)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
