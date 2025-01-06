---
title: "Bypass Win 10 Password - (On Screen Keyboard)"
---

If you have forgot your password and stuck at this screen,

![win1](/assets/images/win1.jpeg)

Here's a solution to bypass win 10 password and all you need is a windows installation media ( a pendrive or CD/DVD) which you can make with  win 10 iso and write it on pendrive with rufus software OR there are many youtube tutorials out there to make windows installation media , it's very easy 

NEXT, 

restart your computer and boot into the removable media ( pendrive, CD/DVD ) which contains the windows installation thing,
Here's a solution to bypass win 10 password and all you need is a windows installation media ( a pendrive or CD/DVD) which you can make with  win 10 iso and write it on pendrive with rufus software OR there are many youtube tutorials out there to make windows installation media , it's very easy 

NEXT, 

restart your computer and boot into the removable media ( pendrive, CD/DVD ) which contains the windows installation thing,

![win2](/assets/images/win2.jpeg)

Click NEXT (Don't worry your all files will be safe, we are not installing windows)


 then,

![win3](/assets/images/win3.jpeg)

 click on Repair your computer,

![win4](/assets/images/win4.jpeg)

Now choose Troubleshoot and hit enter,

![win5](/assets/images/win5.jpeg)

open Command Prompt,
and TYPE : copy **C:\Windows\System32\cmd.exe C:\Windows\System32\osk.exe**
this will copy command prompt (**cmd.exe**) from bootable media to your computer in place of On Screen Keyboard (**osk.exe**) which is present in the lock screen

![win6](/assets/images/win6.jpeg)

now type exit,
and reboot into your windows 10 operating system to change the password

![win7](/assets/images/win7.jpeg)

Now , select the On Screen keyboard and your command prompt will open up like this,

![win8](/assets/images/win8.jpeg)

now TYPE: **net user** and see which user you want to login (in my case its **pd** )

![win9](/assets/images/win9.jpeg)

then type : net user pd  * (to make changes that is to change password)

![win10](/assets/images/win10.jpeg)

now type new password ( whatever you want )
and then re-type it

![win11](/assets/images/win11.jpeg)

**CONGRATULATIONS !!!** You have changed your password without losing your files and now you can log in to your account. 


