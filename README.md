# project-7
## DEVOPS TOOLING WEBSITE SOLUTION

## prepare NFS server

![Capture3](https://user-images.githubusercontent.com/108102087/190637352-f50bed96-7bdf-4d07-b257-b02a865f8494.PNG)

![Capture](https://user-images.githubusercontent.com/108102087/190677722-7c39f14c-4475-4dfa-871d-e8d048e48e8a.PNG)

Configure access to NFS for clients within the same subnet.

![Capture5](https://user-images.githubusercontent.com/108102087/190678955-2a4aa4a2-e940-4022-8420-c1c0018322cc.PNG)

Check which port is used by NFS and open it using Security Groups (add new Inbound rule)
![Capture4](https://user-images.githubusercontent.com/108102087/190678224-2afeb9bb-112f-4d3d-8a97-a70b2ecad80c.PNG)




## CONFIGURE THE DATABASE SERVER
i install and configure a MySQL DBMS to work with remote Web Server

Install MySQL server
Create a database and name it tooling
Create a database user and name it webaccess
Grant permission to webaccess user on tooling database to do anything only from the webservers subnet cidr

![Capture2](https://user-images.githubusercontent.com/108102087/190636487-dc70a3f5-0537-4fbc-a37a-4d01e508d1b2.PNG)

Verify that Apache files and directories are available on the Web Server in /var/www and also on the NFS server in /mnt/apps. If you see the same files – it means NFS is mounted correctly. You can try to create a new file touch test.txt from one server and check if the same file is accessible from other Web Servers.

Locate the log folder for Apache on the Web Server and mount it to NFS server’s export for logs. Repeat step №4 to make sure the mount point will persist after reboot.

Fork the tooling source code from Darey.io Github Account to your Github account. (Learn how to fork a repo here)

Deploy the tooling website’s code to the Webserver. Ensure that the html folder from the repository is deployed to /var/www/html

Note 1: Do not forget to open TCP port 80 on the Web Server.

Note 2: If you encounter 403 Error – check permissions to your /var/www/html folder and also disable SELinux sudo setenforce 0
To make this change permanent – open following config file sudo vi /etc/sysconfig/selinux and set SELINUX=disabledthen restrt httpd.

![Capture6](https://user-images.githubusercontent.com/108102087/190679625-c1bcdc78-e782-4115-9414-4edd0a9285ea.PNG)

![Capture7](https://user-images.githubusercontent.com/108102087/190713711-c9069eb9-4675-4844-83cf-2b4ac19f4a98.PNG)

![last text](https://user-images.githubusercontent.com/108102087/192879013-b3334ea2-2bc7-4aec-8061-fdfd958c2063.PNG)
