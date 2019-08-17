# Administrator's Cookbook
A collection of useful commands, snippets, and reference links used in the average day of an administrator.

Please note these are only based on my personal experiences. 
These commands are intended to be used as reference material, for the purposes of refreshing your memory. If you don't know what a command does, don't run it until you've looked it up and understand what it does.

Please also feel free to check out my [Developer's Cookbook](https://github.com/liaocanada/Developers-Cookbook).

## Table of Contents
1. [Linux + Mac](#linux-mac)
2. [Windows](#windows)
3. [VMs](#vms)
4. [AWS](#aws)
5. [Google Cloud](#gcloud)
6. [Docker + Kubernetes](#docker-kubernetes)
7. [MySQL](#mysql)
8. [Default Port Numbers](#ports)

## <a name="linux-mac"></a> Linux + Mac
| Action                                                                   | Command                                                                                                                                                                                                                                                                 | Description |
|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Basic commands                                                           | `cd <destination>`<br/> `ls`<br/> `pwd`<br/> `sudo su`<br/> `ping <url>`<br/> `curl <url>`<br/> `mkdir <new-directory-name>`<br/> `echo "<text>" > <destination-file>`<br/> `touch <new-file-name>`<br/> `cat <file>`<br/> `vi <file>` or `vim <file>` or `nano <file>` |             |
| Basic vi/vim                                                             | After pressing `<esc>` twice:<br/> `:q`<br/> `:wq`<br/> `i`                                                                                                                                                                                                             |             |
| Deploying an Express server                                              | [Install node+npm](https://github.com/liaocanada/Developers-Cookbook/blob/master/README.md#node---installation)<br/> [Copy code using scp](#)<br/> `npm install -g forever`<br/> `forever start <app-root>/server.js`<br/>                                              |             |
| Apache web server reverse  proxy config                                  |                                                                                                                                                                                                                                                                         |             |
| Nginx reverse proxy config                                               |                                                                                                                                                                                                                                                                         |             |
| URL Redirect using  iptables  (using reverse proxy  is more recommended) | `sudo iptables -t nat -I PREROUTING -p tcp --dport 80 -j REDIRECT --to-port <redirect-port>`                                                                                                                                                                            |             |

## Windows

## VMs
| Action             | Command                                                                                                                                                                                                                                 | Description                                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| SSH to an instance | `ssh -i <private-key-location> <user>@<public-dns-or-ip>`<br/> `ssh -i my-private-key.pem ec2-user@ec2-12-123-23-234.compute-1.amazonaws.com`                                                                                           | `<user>` for EC2:<br/> Ubuntu = `ubuntu`<br/> Centos = `centos`<br/> Debian = `admin`<br/> Other Linux = `ec2-user` |
| Copy files         | Zip up source folder<br/> `scp -i <private-key-location> <source>.zip <user>@<public-dns-or-ip>:<destination-directory>`<br/> Connect to instance via ssh<br/> `cd <destination-directory>`<br/> `unzip <source>.zip`                   |                                                                                                                     |
| Mount a volume     | Attach the volume via EC2 console or equivalent<br/>`lsblk`<br/> `sudo file -s <volume-name>`<br/> `sudo mkfs -t ext4 <volume-name>`<br/> `sudo file -s <volume-name>`<br/> `sudo mount <filesystem-name> <destination-directory>`<br/> | `<volume-name>` for EC2 might look like `xvdb` or `sdb`<br/> `<filesystem-name>` might look like `xvdb1` or `sdb1`  |

## AWS

## <a name="gcloud"></a>Google Cloud

## <a name="docker-kubernetes"></a> Docker + Kubernetes

## MySQL
| Action                      | Command                                                                                                                        | Description |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------|-------------|
| Connect to MySQL CLI        | `mysql`<br/> `mysql --user=<user> -p`                                                                                          |             |
| Export a database           | `mysqldump --user=<user> -p <DB-to-export> > <destination-file>.sql`                                                           |             |
| Import a database           | `mysql --user=<user> -p <DB-to-import> < <source-file>.sql`                                                                    |             |
| Display contents of a table | Connect to MySQL CLI<br/> `show databases;`<br/> `use <database-name>;`<br/> `show tables;`<br/> `select * from <table-name>;` |             |

## <a name="ports"></a>Default Port Numbers
| Name              | Port Number   |
|-------------------|---------------|
| Apache Tomcat     | 8080          |
| Express           | 5000 or 3000  |
| React             | 3000          |
| Angular           | 4200          |
| Apache Web Server | 80            |
| Nginx             | 80            |
| RabbitMQ          | 15672         |
| Available ports   | 1024 to 49151 |
| Possible ports    | 0 to 65535    |
