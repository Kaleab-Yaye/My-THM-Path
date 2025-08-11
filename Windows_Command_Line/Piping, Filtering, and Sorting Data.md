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
now as i have told you before the workign off command like get-service is to return al the obejct one by one this mean the command that is on th eothere side of the pipline should deal with them one by one. this opens an aportunity an aportunity to filter the object not to sort them but to filter them.

so the sysntx usually look like this
```powershell
<sommegetcommand> | where-object {$_.-<property_of_bject> -<comparison parameters> <the proporty you wan to much>}
```
now the thign you shoudl know is the varibal $. representtes the object that is currently in the pip line.

now for the comparsion parameters.
PowerShell's comparison operators are designed to be readable.
-ne: Not equal
-gt: Greater than
-lt: Less than
-ge: Greater than or equal to
-le: Less than or equal to
-like: Like (uses wildcards *). Case-insensitive by default.
-notlike: Not like.
-match: Matches a regular expression. Case-insensitive.
-notmatch: Does not match a regular expression.
-contains: The collection on the left contains the item on the right.
-in: The item on the left is in the collection on the right.

now you can look up for how each is used but lets do the following exersis to see how it is actually used
1. Scenario: The Rogue Executable. You are a junior security analyst investigating a machine. You suspect a piece of malware is running, and you've been told its name is "invader.exe", but you're not sure. You want to find any running process whose name contains the word "invader". What single command would you use?
***answer***
so we are not going to use the eq oprator here since we are ooking for invader, but if we where to us ethe eq it would mean the file name has to be exactly invader
nothign more nothign less so we will use the -like oprator
```powershell
 get-process | where-object {$_.name -like "*invader*"}
```
this will show as all the restults containign the key word invader;

# Reshaping Objects with Select-Object
ok so lets say you wnat to display the porporites fo a proces then you would see things like name pid and so on. but the thing is you can do alo tthatn that you can choose which proprteis of the object you can see adn also you can rename and do cualucaltion on those poprites you want displed

for this we wnat the select-object it is not select an obejc the name is confuesing but it showign as the select propoties.

the syntax is
```powershell
[the command that will return the object] | get-object [-propertey <stystem.object>[]]
```
exmaple
```powershell
get-services |select-object -property name
```
this will show us the list of obejcts with only the protey name on display

you can also use the slect object with 
```
select-object -firts/-last N
```
to slect the first N object or the las N object you see it can be used to reduce the row as well as the colomon( it can make sure only fiew proprtyes stay with teh object and it can alo make sure only some of thos object would servive

the follwoign is an adanved exmpale of how to use the selct object
```
Get-Process | Select-Object -Property Name, @{ Name = 'Memory(MB)'; Expression = { $_.WS / 1MB } }
```
try to explain it youself.

lets try the follwoign exersise..

1.ask: Creating a File Report. You need to generate a simple report of all the .dll files in the C:\Windows\System32 directory. The report should only contain two columns: the file's name (Name) and the last time it was written to (LastWriteTime). What single command would produce this report?

2. Tricky Question: Pipeline Order Matters. Consider these two commands. Will they produce the same result? If not, explain what each one does and why they are different.
Command A: Get-Process | Select-Object -First 10 | Sort-Object -Property CPU -Descending
Command B: Get-Process | Sort-Object -Property CPU -Descending | Select-Object -First 10

3.The Analyst's Challenge (Calculated Property): You are analyzing file sizes. You want a list of files, but instead of showing the size in bytes (the Length property), you want to show it in Kilobytes (KB). Write a command that lists all files in the current directory, showing only their Name and a custom column named Size(KB) that you calculate yourself.
answer.

1.there are two ways to do this
methodeone: 
```powershell
get-childItem -path C:\Windows\System32 -name "*.dll" | select-object -property name , LastwriteTime
```
or
```powershell
get-childItem -path C:\Windows\System32 -recurse | where-object {$_.name -like "*.dll"} | selct-object -property name,LastwriteTime
```
2. now they wotn give you the same out come. the first one will selct the first 10 object bassed on the there sorted name oerder or any defualt that is for porccess . then it will sort it bassed on cpu in desentin manner
 but the secon one firt sorts the procces in desdign order bassed on there CPU usage and then teh selct object will sselec tthe up most 10 object (processes)
3 
```
get-childItem -recurse | slect-object -property naem, @{Name:size ; exepression = {$_.Length/kB}}
```


get-childItem | where-object {$_.length -lt 100}
get-childItem | where-object -property length -lt 100




