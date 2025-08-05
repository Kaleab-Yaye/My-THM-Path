# Basic system information
##### note, 
i thought ssh was only for linux bassed sytems but it is alo a way to get the CLI in windows and the the cmd.exe is the command line enterprator for windows.
# THings i learn in this room
* "set" command is use to display all the sytem varibale that are present for use.
  all the cahnges you make with the set comman over ssh are temporary and you would need the setx command to make it permanent
* "ver" command is used to see the version of widnows of the windows device that you are connect to through the ssh

* "systeminfo" this one is used to see all the system specifcatuion of the sshed windows computer

# Network trouble shootin;
in the cmd or on the termianl you sshed to you can use the command 
```bash
ipcongig
#or for more detail
ipconfig /all
```
quick reminder you might need to come back and look  at this
<img width="1114" height="446" alt="image" src="https://github.com/user-attachments/assets/519c8bea-c3ed-4522-a8b2-226cca99c62c" />

##tracert( trace rout);
thisis another tool that we use to anlise the stat of our conneciton with a server of our chooing
the command goes like this 
``` bash
tracert example.com;
```
now the internat is build upon rougther ablity to rought our packets from one place to the othere till the final server is reached( the routing is handeld by a complex logic but is the shortes one till told othere wise) 
and this command is used to count those many hops.

not this is possible beacouse of the packet called the TTL( time to live ) it is not time counter but it is actually hope counter.
now when you run this command your host will sedn a TTL packet with 1 value. noe by defaul a router is ment to decriment the ttl value and forward it to the next( expet if it is 1 or 0) till it reach teh destned server
but if it is 0 or 1 it send a packet to our host saying time to live has been exeded.
now the only serve that wotn send the time to live has exided is the exmaple.com but untile it reach there reciving the time to live has exprie is used to count the hops look at htis one for exmpale;

<img width="891" height="482" alt="image" src="https://github.com/user-attachments/assets/f26f1ffe-f118-46ab-ad11-e930a7870af1" />
now as you can see the very first routers risponded with the TTL is dead responce when we sent it TTL wiht 1 value and we sent this three time to make sure
but the subsquent routers said nothing. this is becouse for security reasons those routers are ment to never rispond to such hits. but they will kiipe forwarding the ttl packet as long as it is not 0 or 1 they wont just tell us
when it is 0 or 1( meaning we dont know how logn it took for the packet to reach tartget or what it is)
then the 9th rougehr ripoded with the TTL has dide risponce and we new it took 9 hops to reach there.
so from the image you can see it took 15 hops to reach the server.

## now i was asekd this "What is the name of the process listening on port 3389?"

so the las thsi that you shoudl is the netstat -abon command this list all the ongoing procces relted to a specifc port that is listening 
so i used
```shell
netstat -abon
```

so i used that but the  thign is i cant se ethe owner of that port but i can see the PID so i use this commadn to locate what runnign service have owner shiip of the port using 
```shell
tasklist | findstr "<the pid i just foudn>
```
adn this listed the owner of the port.


# navigating files

the windwos CLI is very simmlar to the one we know on linux
you can use the 
* cd; to to go the dir you want
* dir; to lis the dir there
* dir /a ; to list even hiden sub dir
* dir /s ; to list all the sub dir of sub dir
* mkdir ; to creat directory
* rmdir ; to remove a dir
* erase or del ; to remoce a file
and just knwo that the . is the curren directory and the .. is the super direcotory

you use the 
```bash
move <the file you want> <to the directory you want
#to move files
```

you use the more or type, bur perifabbly more to deciplay texts( or any UTF-8 file type) 
exmaple
```bash
C:\>more server.log
```

### NOTE
we have said you can list alll task with the command

tasklist;

now to kiil a tasklist
noq to kill a task you use 
``` bash
kill task /PID <the targt PID>
```



  
