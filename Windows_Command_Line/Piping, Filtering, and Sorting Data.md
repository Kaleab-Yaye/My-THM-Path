# usign the sort-object;

the pipline | is one of the definng futres of powershell.

so now lets say you runt this
```powershell
get-process
````
what you get is a list of all procces btu there is no sorty there what is cougth by the powersell is what will dieplses so now lets sor it usign sort-object

teh sort object has the follwign paraeters
```powershell
-property <Sytem.object[]># this could be cpu namde network or any proporties that our data will be sotred over
# can add many propoties so that the sorting woudl be more effcient
-desnding/asending #
```
```powershell
Get-Process | Sort-Object -Property Name
```
##### how to use the get-memerber command to see the proporites of an object
so look when you run the get-childItem on nont specfied dir it will output all the thins in teh dir but if you specify the object you wna it will return that object

```powershell
get-childItem './downloads/me.exe' | get-member
```
thit will show you every propties that are on a file system. 

now this is a very good exmpale of usign the pipline to sorty stuff

```
 get-childItem -path './my logs' | sort-object -property length -descending
```

# exercis

lets answer this qeusion
The Analyst's Challenge: You want to find the 5 processes on your system that have been running the longest (the oldest processes).
Part A: Which property of the objects from Get-Process would you sort by to find the oldest processes? (You may need Get-Process | Get-Member or Get-Help Get-Process -Full to find this).
Part B: Write the command to sort the processes so the oldest one appears first.

answer:
so first run this command to sort all the proporitess of a procces by name
```powershell
get-process | get-member | sort-object -property name
```
now you can see tehre is this proportie called 
<img width="686" height="23" alt="image" src="https://github.com/user-attachments/assets/2bbefd85-c52f-4da0-a5a4-d74289962851" />

```powershell
#then you run this command
get-process | sort-object -property starttime
```

# filtering with (where-object);



