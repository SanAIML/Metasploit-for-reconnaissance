# Metasploit-for-reconnaissance
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
<img width="1184" height="577" alt="Screenshot 2025-10-03 142254" src="https://github.com/user-attachments/assets/4c7a8d6d-0728-493c-b1b8-0f6be7ac5a08" />


invoke msfconsole:
<img width="1183" height="793" alt="Screenshot 2025-10-03 142311" src="https://github.com/user-attachments/assets/397764bb-1d41-47bb-a63a-659cb480ad10" />


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

<img width="1272" height="907" alt="Screenshot 2025-10-03 142349" src="https://github.com/user-attachments/assets/63610f0e-9d91-4a8f-9b9a-ae4c7586e367" />


## Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000


<img width="893" height="654" alt="Screenshot 2025-10-03 142418" src="https://github.com/user-attachments/assets/0ed205fc-de24-4a2b-afad-afa2e8a7fdbc" />

## OUTPUT:

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

<img width="1415" height="655" alt="Screenshot 2025-10-03 142429" src="https://github.com/user-attachments/assets/f8998c2d-2952-44bf-a2d6-2d2dc1dfda44" />



Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

<img width="1327" height="594" alt="Screenshot 2025-10-03 142442" src="https://github.com/user-attachments/assets/897e238b-efbe-45ae-a1d5-135e7590bd20" />



Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

<img width="1490" height="736" alt="Screenshot 2025-10-03 142505" src="https://github.com/user-attachments/assets/3455fd01-60be-4858-8f5e-30e64017d558" />


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version 

<img width="1202" height="371" alt="Screenshot 2025-10-03 142544" src="https://github.com/user-attachments/assets/87d05c1b-074d-4733-8230-f627ad518077" />


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

<img width="1481" height="629" alt="Screenshot 2025-10-03 142558" src="https://github.com/user-attachments/assets/d35d7df4-f786-4cae-aa20-ab84e07a74f7" />


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true


<img width="1492" height="596" alt="Screenshot 2025-10-03 142613" src="https://github.com/user-attachments/assets/0e5db106-b0a7-4d4d-bc74-b9ebcead2dd9" />

<img width="1474" height="312" alt="Screenshot 2025-10-03 142621" src="https://github.com/user-attachments/assets/9af2dca0-4843-4db7-a8c8-e2ce6f98c161" />


<img width="1489" height="699" alt="Screenshot 2025-10-03 142632" src="https://github.com/user-attachments/assets/423abee7-160d-4cf6-811a-2b012aa2ed02" />



<img width="1416" height="421" alt="Screenshot 2025-10-03 142642" src="https://github.com/user-attachments/assets/8eaddf5f-7a57-4055-949d-fa1f4fa93fde" />








## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
