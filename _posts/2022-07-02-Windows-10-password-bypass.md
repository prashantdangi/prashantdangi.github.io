---
title: "How to Bypass Windows 10 Password Using the On-Screen Keyboard Method"
---

## Introduction

Forgetting your Windows 10 password can be stressful, but there's a solution that doesn't require reinstalling Windows or losing your files. This tutorial will guide you through bypassing the Windows 10 login screen using the On-Screen Keyboard exploit.

![win1](/assets/images/win1.jpeg)

## Prerequisites
Before starting, you'll need:
- A Windows 10 installation media (USB drive or DVD)
- Access to a working computer to create the installation media

### Creating Installation Media
1. Download the Windows 10 ISO from Microsoft's official website
2. Download and install Rufus (a USB bootable drive creation tool)
3. Use Rufus to write the Windows 10 ISO to your USB drive

## Step-by-Step Guide

### Step 1: Boot from Installation Media
1. Insert your Windows installation media
2. Restart your computer
3. Boot from the USB drive or DVD (you may need to change boot order in BIOS)

![win2](/assets/images/win2.jpeg)

### Step 2: Access Recovery Environment
1. Click "Next" on the installation screen


![win3](/assets/images/win3.jpeg)

2. Select "Repair your computer"

![win4](/assets/images/win4.jpeg)

### Step 3: Navigate to Command Prompt
1. Choose "Troubleshoot"
2. Select "Command Prompt"

![win5](/assets/images/win5.jpeg)

### Step 4: Replace On-Screen Keyboard
1. In Command Prompt, enter the following command:

```cmd
 copy C:\Windows\System32\cmd.exe C:\Windows\System32\osk.exe

```

This command replaces the On-Screen Keyboard executable with the Command Prompt executable.



![win6](/assets/images/win6.jpeg)

now type 

```cmd
exit
```

### Step 5: Change Password
1. Restart your computer and return to the login screen

![win7](/assets/images/win7.jpeg)

2. Click the Ease of Access button to open On-Screen Keyboard
3. Command Prompt will open instead

![win8](/assets/images/win8.jpeg)

4. Type `net user` to list all user accounts

![win9](/assets/images/win9.jpeg)

5. Change the password using:

```cmd
net user pd *
```
Replace USERNAME with your account name

6. Enter and confirm your new password when prompted

![win10](/assets/images/win10.jpeg)

now type new password ( whatever you want )
and then re-type it

![win11](/assets/images/win11.jpeg)

## Success!
You can now log in to your Windows 10 account with the new password. All your files and settings remain intact.

## Security Considerations
- This method demonstrates a security vulnerability in Windows systems
- Always set a password you can remember or use a password manager
- Consider enabling additional security features like Windows Hello or two-factor authentication

## Important Notes
1. This method is for personal use only when you've forgotten your password
2. It's not recommended to use this method on computers you don't own
3. Regular backup of important files is always recommended

## Troubleshooting
If you encounter issues:
- Ensure you're using a compatible Windows 10 installation media
- Verify that your computer can boot from USB/DVD
- Make sure you have administrator privileges on the account



