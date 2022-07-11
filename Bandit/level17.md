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
nc localhost 31790
```
Paste the password 
```
 cluFn7wTiGryunymYOu4RcffSxQluehd
 ```
 
 
