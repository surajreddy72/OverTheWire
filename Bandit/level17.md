# Check out ``` man nmap ```

nmap -p <portranges> <IP/host>

-p is used to scan for specified ports

```
nmap -p 31000-32000 localhost
```
But did not get the Services which the ports correspond
The services report that the ports correspond to mail server(SMTP),web server(HTTP),Name server(DNS)
TCP port 25 are main servers

**So for detecting the versions and services of ports we use -sV** 

``` 
nmap -sV localhost -p 31000-32000
```
(takes time)
 
Here we get to know which ports listen to ssl i.e
```
port 31790
```
Then we need to submit our current password to that port 
```
openssl s_client -connect localhost:31790
```
Paste the current password 
```
cluFn7wTiGryunymYOu4RcffSxQluehd
 ```
 Returns you a ***private key***
  
 __Copy the private key__
 
 Now we need to store the private key Remember we cant create a file on current working directory
 So we create our directory in tmp
 ```
 cd /tmp
 mkdir blahblah
 cd blahblah
 ```
 After entering the blahblah directory :
 create a file to save the Private Key
 ```
 cat > blahblah
 ```
 Paste the private key copied and to exit press ctrl + D
 
 Then try to login into localhost using private key
 ```
 ssh bandit17@localhost -i blahblah
 ```
