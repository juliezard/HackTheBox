# Machine: Meow

Ping is a ICMP echo request, this can be used to test for connection
- **ping {target_IP}**
  - **ping {target_IP} -c 4** 
    - Counts 4 echo replies and stop
 
![meow_ping](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_ping.png?raw=true)

Nmap is a tool used to find open ports on a target
- **sudo nmap {target_IP}**
  - **sudo nmap -sV {target_IP}**
    - **-sV** switch stands for version detection 
- telnet is on port 23

![meow_nmap](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_nmap.png?raw=true)

Telnet is a command line interface for communication with a remote device or server
Try accounts:
- admin
- administrator
- root

![meow_telnet](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet.png?raw=true)

Use command **ls** to show directory folders
![meow_telnet1](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet1.png?raw=true)

Use command **cat** (concatenate) to read data from file and output the content

# Machine: Fawn
FTP (file transfer protocol)
- **ftp {target_IP}** 
  - Use command **ls** to list directory folders
  - Use command **get** to download files from remote computer to the local computer
  - Use command **bye** to leave ftp
  - Use command **cat** (concatenate) to read data from file and output the content

# Machine: Dancing
SMB (Server Message Block) port 445
-
