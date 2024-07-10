# Active-Directory-on-Windows-Server
My Active Directory notes

## Introduction of Active Directory
Active Directory is a Microsoft service that provides centralized authentication and authorization to network resources. It’s used in business environments to simplify user management, control access to data, and enforce company security policies.

how it works:
1) Authentication: Active Directory verifies a user’s credentials (username and password). The user’s credentials are stored in the Active Directory database.
2) Authorization: This process grants or denies a user to do something such as edit a file or access an application.

Active Directory is especially useful for companies that have to manage lots of endpoints and servers. It stores information about objects on the network and makes this information easy for administrators and users to find and use. Objects might include user accounts, computer accounts, and resources like file and print servers.

Active Directory Domain Services (AD DS) is the main component of Active Directory. It’s the Server Role in Windows Server that you install if you want to promote the server to a domain controller (DC). DCs host a copy of the AD database and they perform authentication and authorization functions to make resources and data available to network users and administrators.

Active Directory is for almost any company or organization out there. It simplifies life for administrators and end users while enhancing security for organizations. Administrators and end users share the centralized user and rights management, as well as centralized control over computer and user configurations through the AD Group Policy feature.

<br><img src="ad.png" width=40% height="auto"><br><br>

## Windows Server installation on Virtual Box

1) Download the ISO from the following link: https://www.microsoft.com/evalcenter  -> select windows server -> select the version -> click (next to get started) download the ISO -> sign in and download.
<br><img src="down1.png" width=40% height="auto"><br><br>
2) Download Virtual Box and install the OS.


## Configure some settings before installing Active Directory
After installing the O.S. We need configure these settings:

 - Activate windows (start -> control panel -> system and security -> system -> check windows status, if activeted -> ok, else -> click on active windows)
 - Rename the computer name to RTS-DC1 (server manager -> local server -> click on computer name and rename it)
 - Change the network to internal (DEVICES -> NETWORK SETTINGS-> select INTERNAL NETWORK)
 - Set a static IP address (Network and Internet -> Network Connections -> right click on ethernet properties -> double click on tcp ipv4 -> and set up an static ip address 192.168.1.250 -> subnet 255.255.255.0 and dns server 192.168.1.250)
 - Mouse integration (in alto di virtual box -> mouse integration)
 - To Unlock the windows server (insert -> ctrl+alt+del)

Check your configuration in local server
<br><img src="setting1.png" width=40% height="auto"><br><br>



## Active Directory Overview e Terminology
 - Domain -> collection of objects (users acc,computers acc, groups… and more)
 - Domain Controller -> server with the active directory installed)
 - Tree -> collection of a domains
 - Forest -> collection of trees
 - Global Catalog -> it’s a central repository containing a subset of attributes of all objects in the AD forest.
 - DNS -> resolve a name to ip address


## Methods to install Active Directory 
 - Powershell (install windows feature AD Domain Services and ADDSDomainController)
 - Server Manager (Add roles and features)
 - DCPromo /Unattend: <path> (with a file, minimize errors)


## Active Directory installation
To install AD go to: manage -> add roles and features
<br><img src="i1.png" width=40% height="auto"><br><br>
<br><img src="i2.png" width=40% height="auto"><br><br>
<br><img src="i3.png" width=40% height="auto"><br><br>
<br><img src="i4.png" width=40% height="auto"><br><br>

Click next until install.

### Domain Controller Promotion
After installation will pop up a warning 
<br><img src="warning1.png" width=40% height="auto"><br><br>
Click on Promote (it will promote the server in domain controller)
Follow the images below:
<br><img src="d1.png" width=40% height="auto"><br><br>
<br><img src="d2.png" width=40% height="auto"><br><br>
<br><img src="d3.png" width=40% height="auto"><br><br>
In the first installation it will install the dns, so let uncheck if first installation.
<br><img src="d4.png" width=40% height="auto"><br><br>
<br><img src="d5.png" width=40% height="auto"><br><br>
<br><img src="d6.png" width=40% height="auto"><br><br>
Click next until finish and reboot the system.

### Verify your installation
You can see in your log screen your domain.
<br><img src="v1.png" width=40% height="auto"><br><br>
Another check to do:
server manager -> Tools -> Active Directory Users and Computers -> it's present the domain RTS.LOCAL.
<br><img src="v1.png" width=40% height="auto"><br><br>







<br> <br>
# Author
<b>Xiao Li Savio Feng</b>
