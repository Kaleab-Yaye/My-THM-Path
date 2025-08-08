# powershell

```Powershell
Get-command
```
you use this command to see all the commands that are availble.

now you can filleter with 
```Powershell
Get-command -noun *you desired command*
Get-command -verb * your desired aciton*
```
## comand type
when you run the get-command you are get all those type of command 
* cmdlet; those are the built in powershell commands
* Funcion; this type of command is usually user build or foudn in helper toold for power sheell and they mostly are usable code blocks
* Applicaion; those commands are the once that are realted to the installed software on the system and application when you run th ipconfig you are running the
  ipconfig.exe
* Alies; // we will see them shortly

but the pioint is you can filtter those commands by those types example look at this 
<img width="1075" height="153" alt="image" src="https://github.com/user-attachments/assets/d5fda67c-7d44-4e5f-860e-1f920412039f" />
**NOTE** powersheell 99% of thhe time is case sensetive 

now you can combien the all
```Powershell
get-command -commmantype application,cmdlet -noun service,user -verb shutdown,restart
```
this is we are askign power shell to pull as all the command that is command tyype applictoin or cmdlet and the nount is sercvice or user and the verb is shutdown or restart.
when yous see coammands that are separated by comma just know what they are lists in powershell.
> we might use the ** to look for every thin tha envloves the key work
```
get-command -noutn User #this woudl only look for thos containign the exact User key word
get-user -noun *User*  # user uSer useR would be displayed.
```
#asking help
now you have goudn a command and you want to knwo hto to usse it what you do is you run this line to 
```
Get-help <the command you want to investigate>
```
now get help my not work on the modle so what you do is like this
![Uploading image.png…]()


now what you do is run 




