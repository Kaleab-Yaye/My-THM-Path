# The Workforce - Analyzing Processes and Services.

so we have seen taht the get-service and the get-procces are on of the funsametn command you can use to asse the state and the active state of you pc now we will look at the in some way

##  get-service 

you use this to get all the srvices taht are running on your pc and the command is

```powershell
get-service
````
now lets see the syntax and all the parameters for this command.

it takes the parameter -Name which can use wild card to filter the services

```powershell
get-service -name "* what ever you want here*"
```
### now how do you filter those bassed on there proporties?
well you sue the where-obeject commadn to clean them and filter them but the thing is when you watn to use it you have to knwo what proportie that you shoudl use and aldo knwo the state that the propery can be in.
so lets see how we can do this. first do this

```powershell
get-service | get-member
```
now this will show yo uall the proptes of the very fist proceses not with there valeus but what they are. then what you need to do is loo for tht propert and copy the path you see here.
<img width="1205" height="28" alt="image" src="https://github.com/user-attachments/assets/098fc3c7-e23a-48db-86e6-fef3e8820024" />

```powershell
[System.Enum]::GetNames("the definition goes here ) # for exmpale for the definition statutues this would look like
>>[system.Enum]::getnames([System.ServiceProcess.ServiceControllerStatus])
```
now what you woudl see in the terminal would look like
<img width="1215" height="245" alt="image" src="https://github.com/user-attachments/assets/7bed2d90-2ecf-4d70-b057-71786d0403e1" />
now you can use the possible states of that proporty of a service or a procces to filter thme out whichc we have done so many time with the where-object command.

# the network

so we have seen before that the netsat is the classic tool to prop the connection in our system but now in ps we have even btter obejct drive command called *** get-NetTCPConnection ***
now it is up to you to see how to use i did and it is preety easy not that muhc of a fusse but lets try this.
lets find a tcp connection with a procces id and then we will use the prosses id to see which proces it actaully belongs to

# the finger print
Get-FileHash -Path C:\path\to\some\file.exe
...
....
....
...
.
.
.
.
..
.






