### 1. How to print the login names of all users on a system? 
/etc/shadow file has all the users listed.   
awk –F ':' '{print $1}' /etc/shadow|uniq –u

### 2. Write a shell script to get current date, time, username and current working directory.
```shellScripting
#!/bin/sh
echo "Hello, $LOGNAME"
echo "Today's date is `date`"
echo "Username is `who i am`"
echo "Current directory is `pwd`"
```
### 3. How to check if a directory exists?
```
#!/bin/sh
if [ -d $mydir ]
then
echo "Directory exists"
fi
```
### 4. Explain the file permissions.
r – read 4
w – write 2
e – execute 1

### 5. Given a file, replace all occurrence of word “ABC” with “DEF” from 10th line till end in only those lines that contains word “MNO” 
sed –n '10,$p' file1|sed '/MNO/s/ABC/DEF/'

### 6. How will you find the 19th line of a file using only tail and head command? 
tail +19 file1|head -1 

### 7.  I want to create a directory such that anyone in the group can create a file and access any person’s file in it but none should be able to delete a file other than the one created by himself. 
We can create the directory giving read and execute access to everyone in the group and setting its sticky bit “t” on as follows: 
mkdir direc1
chmod g+wx direc1
chmod +t direc1
### 8.  How to get the 3rd element/column from each line from a file?   
#!/bin/sh
awk '{print $3}' $1
### 9. How to pass arguments to a script?
```
./script.sh  file.txt
cat script.sh
#!bin/bash
Cat $1
```
### 10. How to use arguments in the script?
In the script we use first argument as $1 and second argument as $2 
Example: To move file one destination($1) to another($2)
```
./move.sh file.txt /text
cat move.sh
#!/bin/bash
mv $1 $2
```
### 11. How to add two strings?
```
S1=”hello”
S2=”world”
Let s3=$s1+$s2
Echo $s3
```
### 12. Write a script to check if a file exists on the system?
```
If [-f /var/www/html]
Then 
Echo “file exists”
Fi

```
### 13. From given file name find the count of lines containing word  “ABC”
grep –c “ABC” filename

### 14. How to print all array indexes?
echo ${!array[@]} used to print all array indexes.

### 15. Write a script to compare numbers?
```
#!/bin/bash
X=10
Y=20
If [ $x –gt $y ]
Then 
Echo “ x is greater than y”
Else 
Echo “y is greater than x”
Fi
```
### 16. Write a script that receive input from user.
```
#! /bin/bash
Echo  –n  “enter input:”
read input
echo “ you entered: $input”
```
### 17.  Write a script using the AND operator.
```
#! /bin/bash
Echo –n “enter number:”
read number
if  [[ ($number  –lt 10 )  && ($number%2  –eq  0)]]
echo  “even number”
else 
echo “odd number”
fi
```

### 18.  Write an example of OR operator.
```
#! /bin/bash
Echo –n “enter any number : “
read n
if  [[ ( $n –eq 10 || $n  -eq 45) ]]
then 
echo “ you win”

else  “ you lost!”
fi
example of elif 
#! /bin/bash
Echo –n “enter number :”
read number 
if  [[ $number  -gt 10]]
then 
echo “number  is greater than 10”
elif  [[ $num –eq 10 ]]
then 
echo ‘number is equal to 10”
else 
echo “ number  is less than 10”
fi
```
### 19. 71. Write a script for adding multiple values.
```
#! /bin/bash
Sum=0
For (( counter=1 ; counter<5 ;counter++))
Do
Echo –n “enter your number”
read n
(( sum+=n))
#echo –n “$counter”
Done 
Printf   “\n”
echo  “result is : $ sum”
```

### 20. How to send mail using shell script?
```
#! /bin/bash
Recipientadmin@example.com
Subject=”script”
Message=”this mail send by script”
‘mail –s $subject $recipient <<< $message’
```
### 21. Write script to print current date and time.
```
#! /bin/bash
year= ‘date +%Y’
month=’date  +%m’
day=’date +%d’
hour=’date +% H’
minute=’date +%M’
second=’date +%S’
echo ‘date’
echo  “current date is :$day-$month=$year”
echo  “current time is :$hour:$minute:$second”
```

Monitoring your Linux system.
Data backup and creating snapshots.
Dumping Oracle or MySQL database for backup.
Creating email based alert systems.
Find out what processes are eating up your system resources.
Find out available and free memory.
Find out all logged in users and what they are doing.
Find out if all necessary network services are running or not. For example if the web server failed then send an alert to the system administrator via a pager or an email.
Find out all failed login attempts, if login attempts are continued repeatedly from the same network IP automatically block all those IPs accessing your network/service via firewall.
User administration as per your own security policies.
Find out information about local or remote servers.
Server configuration.
