# mixed
A mixed pot

## iftoip - perl and bash versions
Select an interface by name instead of ip address
```
v@juno:~$ iftoip ens33
10.251.17.94
v@juno:~$ iftoip ens34
192.168.78.128
v@juno:~$ echo "IP=$(iftoip ens33)"
IP=10.251.17.94
v@juno:~$ iftoip ens35 #perl
No such device: ens35 at /home/v/bin/iftoip line 10.
v@juno:~$ iftoip ens35 #bash
Device "ens35" does not exist.    
```
This can be used with any tool that allows you to bind to an interface from the commandline, for example
`ssh -b $(iftoip ens33) user@host`
or
`scp -o BindAddress=$(iftoip ens34) REAME.md user@host:`
