# Get-location
this  used to see what location in and the directory you are workign on
it is closest crosspodance is the pwd in linux
# set-location
it is used to set the workign directory it is alias is cd
you can use the set locaton in to even system varibales and Windows keys usign the command
```powershell
set-location Env: #this nwo will tatk you to the system enviroment and you can work from there
```
# get-childItem
this is used to to see the childe folders and directories and files even the hidden once with parametrs. get-child has some usfull parameters to it
* -path. this is positional parametrs but is also usfull to know
  ```powershell
   get-childItem -path  C:\Users\Administrator\searches
  ```
* -filter this is used to fileter the name of the directory or fiels you want to look for
* -force ; this parameter makes sure that the get-child command displyes even the hidden folders and directoryes
* -recurse; this is applyed over the fileter and the -force now, what hsi does it makes sure the directoryes and the sub direcotryes are list and eveyr thign is showsn
* -file/-direcotry
```
 get-childItem -path  C:\Users\Administrator\download -filter "*.mp4" -recurse
```
# creating and deleteing files and directoryes;
## new-Itme ; this is an object that will hodl all the inforamtion of the Itemtype that we need to creat it take many parrameters and you can look the up
but the parmeter that you will use is 
```cmd
[-path <System.String[]] # as you can see it can take path can take many parameters
[-itemType <stystem.String] # and you can choose "file" or "directory"
```
look at this use example

```powershell
 New-Item -Path "C:\Users\Administrator\desktop\aha1","C:\Users\Administrator\downloads\aha2" -itemtype "directory"
```

## remove-Item
this command is used to remove what ever you specified
it has the follwoign parameters
```Cmd
[-path<System.strig[]] # you can remove many itedms at once
[-recurse] # this shows you all the child dr and there contents
[-whatif] # this one shows you what woudl have happened if you where to perform the command.
```
use what if with -recurse to see all the thign that the reomve-item commadn would have done.

# readign and writign contents of files
## get content to read files
here are the parammeter for the get-content command and wha they do
```cmd
[-path ]<system.Strign[] # meaning you can open many files togtehre
[-head <system.int32] # you can tell powersell which first parts you want it to read
[-tail <Strytem.int32[ # you tell powersell which last part of line you want it to read]
[-wait] # you use this one when you want to inspec the file in realtime.
```
and ecmpel of the use case 

```powersell
get-content "logs" -wait
```
now what this will do is inspect the log file for new upadate.
## set content to overigh a content with a content
the parameters for set-content are ( the most comment once
```cmd
[-path] <System.Strign[] # you can overrite many files at the same time
[-value <system.String>] # this is the value that we will right
[-whatif] # this when you want to be sure wha tyou want to do and it makes sure you undertand
```
## add content
[path parameter]
[-value parameter]



