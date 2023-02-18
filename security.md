# owasp top 10
# security tools
# ncat

## to transfer files
on machine receiving data
`ncat -vl 44444 > out.txt`

on machine sending data
`ncat 172.20.239.129 44444 --send-only < docker.txt`

https://www.linuxtechi.com/nc-ncat-command-examples-linux-systems/
