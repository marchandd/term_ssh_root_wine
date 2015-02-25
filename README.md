# marchandd/term_ssh_root_wine

marchandd/term_ssh_root_wine [Docker:copyright:](https://docs.docker.com/ "Docker") image

## Description

A sandbox container with wine 1.7 ready for settings from Linux or Windows host.

### Goal

Easy method to produce a GUI containers to access to Wine and able to download apps with Firefox into sandbox from secured host to remote client with SSH.

### Image size

Around 1400 Mb.

### References

[Marchand D. Maintainer](https://github.com/marchandd/ "Maintainer")

[Details source](https://github.com/marchandd/term_ssh_root_wine/ "Details")

[Part of project studies](https://github.com/marchandd/docker_index/ "References")

## Build image

### Command line

:computer: `docker pull marchandd/term_ssh_root_wine > build.log`

### Command line explanation

Search password value into build.log file to access later to container.

### Firewall

:warning: If your Firewall is enabled on the host, with default outgoing policy turned to 
deny, 
you will have to disable 22 port filtering:  
- Make a new rule for OpenSSH (22/TCP) to enable outgoing policy.

## Build container

### Command line

:computer: `docker run -d -p XXX.XXX.XXX.XXX:YYYYY:22 marchandd/term_ssh_root_wine`

Where XXX.XXX.XXX.XXX is your IP v4 address.  
Where YYYYY is your Private port, if you doesn't know free port, try from 49200...

### Command line explanation

- Run in detached mode.
- Export port 22.

## Container usage

### SSH access

Open terminal with root/administrator account.

:computer: `ssh -X root@XXX.XXX.XXX.XXX -p YYYYY`

### Alias

When you are into SSH access.

:computer: `firefox`

Wine is installed but need to be initialized before using it with:  
:computer: `/usr/local/sbin/_installFirst_winetricksOptions.sh`

## Explanations

### Dockerfile

- Set architecture x86 and point repository to ppa.
- Install Wine, Winetricks (Wine settings) and CabExtract (for Windows CAB file).
- Make dynamic root password and display it into logs.
- Change config for SSH daemon.
- Give Supervisor management for OpenSSH server.
- Expose SSH port.

### Display

Make sure to have installed OpenSSH client or GUI SSH client (Putty).

### Risks

Root account from container is exposed.  
A password is used and not a certificate that could be more secure.
