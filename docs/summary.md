Complete image to run Wine application through SSH with X11 forwarding display
==========================================================================

Return to [index](https://github.com/marchandd/term_ssh_root_wine/ "Index")

Docker image from Ubuntu 14.10 edition image to run Firefox and
Windows software through emulator accessing by view remotely X displays.

Dockerfile explanation
----------------------

### Installed software

Installed software and settings for Ubuntu 14.10 edition are:
- x86 only restriction for Debian packaqes install.
- OpenSSH to view remotely and interact with target X displays.
- Dbus-x11 system bus display.
- Firefox web browser to be ready capable to search programs/add-ons
  to install...
- Pwgen password generator.
- Wine emulator for Windows software
  with cabextract and winetricks settings helpers.
- Supervisor system to monitor and control processes.
- Python script ready.

### password for root

Scripting the password used for Root user to remote access software.

Script behaviours:
- Automatic generation by default. Password viewed in console output.
- Password is store into local file (in case of password lost) but accessible by Nsenter.
- Script could be changed to modify policy or use static password.

### SSH accessing

Supervisor config to manage OpenSSH software when 22 port exposed:  
- Change config for SSH daemon.
- Give Supervisor management for OpenSSH server.
- Expose SSH port.

Command build image usage
-------------------------

### Command line

:computer: `docker pull marchandd/term_ssh_root_wine`

Command container usage (standalone mode only)
----------------------------------------------

Not necessary to do if you want only to run Portable-Apps Samples image...         
Standalone mode only if you want to do software install by yourself.

### Command line

:computer: `docker run -d -p XXX.XXX.XXX.XXX:YYYYY:22 -v LOCALPATH:/data  marchandd/term_ssh_root_wine`

Where XXX.XXX.XXX.XXX is your IP v4 address.  
Where YYYYY is your Private port, if you doesn't know free port, try from 49200...
In case you doesn't want to share data, just leave "-v LOCALPATH:/data" 
from command line.

### Command line explanation

- Run in detached mode.
- Export port 22.

Container usage (standalone mode only)
--------------------------------------

### Terminal SSH client access

Open terminal with root/administrator account.

:computer: `ssh -X root@XXX.XXX.XXX.XXX -p YYYYY`

### GUI SSH client access

- Open your Putty GUI SSH client.  
- Choose X11 forwarding option into SSH/X11 Configuration and type IPv4:XXXXX remote desktop.  
  XXXXX is your private port you have choose previously.  
- Choose root user and enter password as 'term_ssh_root_wine' for Docker public repository access.

### Remarks

Wine have not been set at the end of install and must been configured in 
first step.  
Enter "winecfg" to do it before first usage. Change settings if you want.  
Now you can try entering "winefile" to verify every thing are functional.

or you can test with my proper config:  
When you are into SSH access.  
:computer: `/usr/local/sbin/_installFirst_winetricksOptions.sh`  
If '/data/' directory is presents into container, a symbolic link is created with "C:\users\Public\Documents" available on Windows Portable-apps.
