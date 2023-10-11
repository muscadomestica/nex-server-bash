# nex-server-bash
Nightfall City's Express Transportation System -- nex:// is a new protocol which serves plain text over port 1900. Here is a server for it

Specifications for this protocol (that I didn't make) can be found [here](https://nightfall.city/nex/info/specification.txt)

## how does it work?
Replace /var/nex with your directory of choice and /var/log/nex with your logfile of choice. run the server like this:
```
tcpserver -v -c10 -p -l 0 -R 0.0.0.0 1900 timeout 5 /path/to/whosnexd
```
Press ctrl + z then type bg

## possible questions
### is it secure?
This server is written in bash! Bash, as I understand it, is relatively insecure in this context, as there is a risk of [command injection](https://en.wikipedia.org/wiki/Code_injection).
I honestly just never wrote a server and it seemed fun! It was :^) I don't know how secure it is, if you don't either then I don't recommend exposing it to the public
### i left this running and disconnected from the server and can't find the active job anymore 
```
pkill tcpserver
```
This might be uncool if you have another tcpserver process running as that user
