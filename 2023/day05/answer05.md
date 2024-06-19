
## 1. You have to do the same using Shell Script i.e using either Loops or command with start day and end day variables using arguments -
So Write a bash script create directories.sh that when the script is executed with three given arguments (one is the directory name and second is start number of directories and third is the end number of directories ) it creates a specified number of directories with a dynamic directory name.

Example 1: When the script is executed as

./createDirectories.sh day 1 90

then it creates 90 directories as day1 day2 day3 .... day90

Example 2: When the script is executed as

./createDirectories.sh Movie 20 50 then it creates 50 directories as Movie20 Movie21 Movie23 ...Movie50

Notes: You may need to use loops or commands (or both), based on your preference . Check out this reference: https://www.geeksforgeeks.org/bash-scripting-for-loop/

### Ans: 

#!/bin/bash

echo "Dir name: "$1
echo "First Dir name: "$1$2
echo "Last Dir name: "$1$3
count=$(($3 - $2 + 1))

for ((n=$2; n<=$3; n++)); do
  mkdir "${1}${n}"
done

echo "Total "$count" directories are created"

## 2. Create a Script to backup all your work done till now.
Backups are an important part of DevOps Engineer's day to Day activities The video in References will help you to understand How a DevOps Engineer takes backups (it can feel a bit difficult but keep trying, Nothing is impossible.) Watch this video

In case of Doubts, post it in Discord Channel for #90DaysOfDevOps

### Ans: 
#!/bin/bash

source="/home/ubuntu/Desktop/devops"
destination="/home/ubuntu/Desktop/backup"

rm -r $destination

echo "Cleared direcotry"

cp -r $source $destination

echo "Backup created in "$destination


## 3. Read About Cron and Crontab, to automate the backup Script
Cron is the system's main scheduler for running jobs or tasks unattended. A command called crontab allows the user to submit, edit or delete entries to cron. A crontab file is a user file that holds the scheduling information.

Watch This video as a Reference to Task 2 and 3 https://youtu.be/aolKiws4Joc

### Ans: 
0 9 * * * /home/ubuntu/Desktop/devops/work/scripting/testb.sh > /home/ubuntu/Desktop/logs/script.log 2>&1
Had time set to UTC changed to HKT timezone and it worked checked logs for testing

timedatectl list-timezones | grep -i "Hong_Kong"

sudo timedatectl set-timezone Asia/Hong_Kong

timedatectl
or
date

## 4. Read about User Management and Let me know on Linkedin if you're ready for Day 6.
A user is an entity, in a Linux operating system, that can manipulate files and perform several other operations. Each user is assigned an ID that is unique for each user in the operating system. In this post, we will learn about users and commands which are used to get information about the users. After installation of the operating system, the ID 0 is assigned to the root user and the IDs 1 to 999 (both inclusive) are assigned to the system users and hence the ids for local user begins from 1000 onwards.

### Ans: 

ubuntu@ubuntu:~/Desktop$ id
uid=1000(ubuntu) gid=1000(ubuntu) groups=1000(ubuntu),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),110(lxd)

ubuntu@ubuntu:~$ su - dev
Password: 
dev@ubuntu:~$ id
uid=1003(dev) gid=1003(dev) groups=1003(dev),1004(test_users)

ubuntu@ubuntu:~$ sudo adduser day5
[sudo] password for ubuntu: 
Adding user `day5' ...
Adding new group `day5' (1005) ...
Adding new user `day5' (1004) with group `day5' ...
Creating home directory `/home/day5' ...
Copying files from `/etc/skel' ...
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: password updated successfully
Changing the user information for day5
Enter the new value, or press ENTER for the default
	Full Name []: 
	Room Number []: 
	Work Phone []: 
	Home Phone []: 
	Other []: 
Is the information correct? [Y/n] y
ubuntu@ubuntu:~$ su - day5
Password: 
day5@ubuntu:~$ 

day5@ubuntu:~$ sudo usermod -aG [groupname] [username]
day5@ubuntu:~$ exit
logout
ubuntu@ubuntu:~$ sudo usermod -aG dev day5
ubuntu@ubuntu:~$ 

dev@ubuntu:~$ id
uid=1003(dev) gid=1003(dev) groups=1003(dev),1004(test_users)

day5@ubuntu:~$ id
uid=1004(day5) gid=1005(day5) groups=1005(day5),1003(dev)


## 5. Create 2 users and just display their Usernames

### Ans: 

dev@ubuntu:~$ cat /etc/passwd | cut -d: -f1 | tail -2
dev
day5
