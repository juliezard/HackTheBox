# Machine: Meow

Ping is a ICMP echo request, this can be used to test for connection
- **ping {target_IP}**

Nmap is a tool used to find open ports on a target
- **sudo nmap {target_IP}**
  - **sudo nmap -sV {target_IP}**
    - **-sV** switch stands for version detection 
- telnet is on port 23, using the username root

FTP (file transfer protocol)
- **ftp {target_IP}**
  - Username: anonymous, password: the service will disregard any password for this account 
  - Use command **ls** to show directory folders
