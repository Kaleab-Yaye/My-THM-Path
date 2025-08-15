well so far we have seen how to command the computer what to do line by line but tthat is actually where ps shines.
like any programing langues we can right line by line instractino fo the computer actino that we want is to perfrom we just need to rigth a clean syntatically logic wise .ps1 file for the cmd and
it will be run when asked
here is an exmpale.

```powershell
write-host "gathering system infomation" 
# this will tell the user that they have to wait some time and our script is actually runnign
# feching network information and connections on the system
get-netTCPConnection | file-out -path 'C:\Users\Administrator\Desktop' - append
# succsesfully registred all the tcp connection on the computer

# featching comupter information for the user

get-computerinfo | select-obeject -property osname, osvertion, totallphysciallmemoy | File-out -path 'C:\Users\Administrator\Desktop\'

# all done and set you can see the result in C:\Users\Administrator\Desktop\'
```



