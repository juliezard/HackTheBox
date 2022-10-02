```sudo apt install {package_name}```

```sudo apt-get update``` downloads the package lists from the repositories and "updates" them to get information on the newest versions of packages and their dependencies

# Machine: Meow

Ping is a ICMP echo request, this can be used to test for connection
- ```ping {target_IP}```
  - ```ping {target_IP} -c 4```
    - Counts 4 echo replies and stop

![meow_ping](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_ping.png?raw=true)

Nmap is a tool used to find open ports on a target
- ```sudo nmap {target_IP}```
  - ```sudo nmap -sV {target_IP}```
    - ```-sV``` switch stands for version detection 
- telnet is on port 23

![meow_nmap](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_nmap.png?raw=true)

Telnet is a command line interface for communication with a remote device or server
Try accounts:
- admin
- administrator
- root

![meow_telnet](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet.png?raw=true)

![meow_telnet1](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet1.png?raw=true)

- Use command ```ls``` to show directory folders

![meow_telnet2](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet2.png?raw=true)

- Use command ```cat``` (concatenate) to read data from file and output the 

![meow_telnet3](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/meow_telnet3.png?raw=true)


# Machine: Fawn
FTP (file transfer protocol) is the network protocol for transmitting files between computers
- ```ftp {target_IP}```

![fawn_nmap](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_nmap.png?raw=true)

![fawn_ftp](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_ftp.png?raw=true)

  - Use command ```ls``` to list directory folders

  ![fawn_ftp1](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_ftp1.png?raw=true)

  - Use command ```get``` to download files from remote computer to the local computer
  - Use command ```bye``` to leave ftp

  ![fawn_ftp2](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_ftp2.png?raw=true)
  
  - Use command ```cat``` (concatenate) to read data from file and output the content

  ![fawn_cat](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/fawn_cat.png?raw=true)


# Machine: Dancing
SMB (Server Message Block) port 445
- ```smbclient -L {target_IP}```
  - ```-L``` will list all services available on the server

  ![dancing_smbclient](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/dancing_smbclient.png?raw=true)
  
  - ```smbclient \\\\{target_IP}\\{sharename}```
  - Trying blank passwords for each share
  
  ![dancing_smbclient1](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/dancing_smbclient1.png?raw=true)
  
  - (IPC$ - The inter-process communication share. Used for inter-process communication via named
pipes and is not part of the file system.)
  - Use command ```get``` to download files from remote computer to the local computer

  ![dancing_smbclient2](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/dancing_smbclient2.png?raw=true)
  
  - Use command ```cat``` (concatenate) to read data from file and output the content

  ![dancing_cat](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/dancing_cat.png?raw=true)


# Machine: Redeemer
- ```sudo nmap {target_IP}```
  - ```nmap -p- -sV {target_IP}```
    - ```-sV``` switch stands for version detection 
    - ```-p-``` to scan ports from 1 through 65535
      - example: ```nmap -p 21-25,80,139,8080 192.168.1.1``` will scan ports 21-25,80,139, and 8080 on ip 192.168.1.1
    
  ![redeemer_nmap](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/redeemer_nmap.png?raw=true)

**Redis** (REmote DIctionary Server) is an open-source advanced NoSQL key-value data store used as a
database, cache, and message broker. The data is stored in a dictionary format having key-value pairs. It is
typically used for short term storage of data that needs fast retrieval. Redis does backup data to hard drives
to provide consistency.

The command-line interface (CLI) is a powerful tool that gives you complete access to Redis’s data and its
functionalities if you are developing a software or tool that needs to interact with it.

There are different types of databases and one among them is **Redis**, which is an **'in-memory' database**. In-memory databases are the ones that rely essentially on the primary memory for data storage (meaning that the database is managed in the RAM of the system); in contrast to databases that store data on the disk or
SSDs

- ```redis-cli -h {target_IP}```
  -  info returns information and statistics about the Redis server

![redeemer_redis](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/redeemer_redis.png?raw=true)
  ![redeemer_redis2](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/redeemer_redis2.png?raw=true)
  - The keyspace section provides statistics on the main dictionary of each database. The statistics include the
number of keys, and the number of keys with an expiration
    - ```select #``` select which key from the keyspace (db0, *select 0*)
    - ```keys *``` list all the keys present in the database
    - ```get <key>``` view the values stored for a corresponding key
    
  ![redeemer_redis3](https://github.com/juliezard/HackTheBox/blob/main/Tier%200/images/redeemer_redis3.png?raw=true)
