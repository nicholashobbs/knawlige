# owasp top 10
# security tools
# ncat

## to transfer files
on machine receiving data
`ncat -vl 44444 > out.txt`

ipconfig -> ipv4 address of machine recieivng data

on machine sending data
`ncat 172.20.239.129 44444 --send-only < docker.txt`

https://www.linuxtechi.com/nc-ncat-command-examples-linux-systems/


use a single multiline comment if you cant have spaces for example in sql


The /etc/hosts file is a local configuration file that maps hostnames to IP addresses. It is used by the local system to resolve hostnames to IP addresses before contacting a DNS resolver. The DNS (Domain Name System) is a distributed system that translates human-readable domain names to IP addresses.

When a computer needs to resolve a hostname to an IP address, it first checks the /etc/hosts file. If the hostname is listed in the file, it uses the corresponding IP address from the file. If the hostname is not listed in the /etc/hosts file, the computer contacts a DNS resolver to resolve the hostname to an IP address. The resolver in turn contacts one or more DNS servers to resolve the hostname.

In summary, the /etc/hosts file is a local alternative to DNS for hostname resolution. It is often used to override DNS lookups or to specify IP addresses for local network services.


# asset discovery

## nmap

## masscan

## amass

## subfinder

## sublist3r

## gobuster

## censys

## shodan

## dnsdumpster

## crt.sh

# content discovery

## dirsearch

## ffuf

## feroxbuster

## waymore

## wfuzz

## waybackurls

## gau

# proxy

## burp

## zap




htb carpe diem

check index.html and index.php , if index.php is there, check for phpinfo.php
if index.html is there it is a static site

click on a link to see how it works - if theres a p=, check for that file .php

if you can put index in the url, it might call itself recursively until erroring out

that means lfi

try putting a comment in the url to test for sql injection
  