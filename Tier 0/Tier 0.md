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
![meow_telnet1](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet1.png?raw=true)

Use command **ls** to show directory folders
![meow_telnet2](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet2.png?raw=true)

Use command **cat** (concatenate) to read data from file and output the content
![meow_telnet3](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet3.png?raw=true)

# Machine: Fawn
FTP (file transfer protocol)
- **ftp {target_IP}** 
![fawn_nmap](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_nmap.png?raw=true)
![fawn_ftp](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_ftp.png?raw=true)
  - Use command **ls** to list directory folders
  ![fawn_ftp1](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_ftp1.png?raw=true)
  - Use command **get** to download files from remote computer to the local computer
  - Use command **bye** to leave ftp
  ![fawn_ftp2](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_ftp2.png?raw=true)
  - Use command **cat** (concatenate) to read data from file and output the content
  ![fawn_cat](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_cat.png?raw=true)

# Machine: Dancing
SMB (Server Message Block) port 445
-
