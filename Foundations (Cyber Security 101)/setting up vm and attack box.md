so the first thign i did is isnstall the vm.
now we will install the linux appliance for kalilinux this is a prebuilt kali linux vetuall box which has .ova file extention

now we donaloded the one that is .vbo and .vdi. 
* the .vbo is the configration file, like base memeroy for the vm and staff
* the .vdi is the hard disk for our kali vm.

now you double clikc onthe .vbo and the mechine will start.

now to make sure that the kali is runnign on its own vetualized world and fully isolated, we can see if the *SATA* is give value of zero.
a computer mothere boards talks to hard disk usign this technology called SATA( serial AT attchment) now the main hard disk is always give a value of SATA:0. if you see this then it means there is now way for the kali
runnign to know it is running on a vertuall enviroment.


##  Configuring the VM Network.
ok so our vm has network interfase card and can make connections but there are three main way how we can set up the network enviroment for our vm
* bridge mode ; in this mdo the vm has it sown nic vsiisble to the roughter menaing it will be give a unique ip address and staff
* NAT mode; (Network Addres translation); here the vm can requist somthign from the outside netwrok like a browser would, it woudl be handeld by the host mechinees os
* Host-only mode; this mode only lets there to be a commnation between the host mechine and the vms, vms in this mode wont be able to connect to the outside world but is good for testing when all teh vm are locally setup

* buw we need the hibrid of Host-only mode and the NAt mode so our attack and target mechines can talk to each othere and download files they want from the internate too

so we will use the NATNetwork.
. go to files, select tools, then netwrok, then go to the natnetwork, click creat save the settings then leave
. go to the mechines selceet your vm and open setting, then scol down to the network setting and add change the networ from nat to NAT Network


## defualt gate way
so let say there is computer runnign a vm runnign a webserver. we want all the computer in the office to reach webserver and make a requist to it but we dont want it to reach the outside entrnate.
now what we would do in this senarion is allow the neworking in the vm to be bridged and then delelet the defualt  gatway adders that the router gave to our vm so that it doesnt know where to send it when it needs to make 
internate connection. that way the server is descverable to every one connected to the work wifi but the internate



