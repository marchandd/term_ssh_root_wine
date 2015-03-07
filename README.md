# marchandd/term_ssh_root_wine

marchandd/term_ssh_root_wine [Docker:copyright:](https://docs.docker.com/ "Docker") image

## Description

A sandbox container with wine 1.7 ready for settings from Linux or Windows host.

### Goal

Easy method to produce a GUI containers to access to Wine and able to download apps with Firefox into sandbox from secured host to remote client with SSH.

### Image size

Around 1250 Mb.

### References

[Marchand D. Maintainer](https://github.com/marchandd/ "Maintainer")

[Details source](https://github.com/marchandd/term_ssh_root_wine/ "Details")

[Part of project studies](https://github.com/marchandd/docker_index/ "References")

### Command line

:computer: `docker pull marchandd/term_ssh_root_wine`

### Firewall

:warning: If your Firewall is enabled on the host, with default outgoing policy turned to 
deny, 
you will have to disable 22 port filtering:  
- Make a new rule for OpenSSH (22/TCP) to enable outgoing policy.

## Build container (standalone mode only)

Not necessary to do if you want only to run Portable-Apps Samples image...         
Standalone mode only if you want to do software install by yourself.

:computer: `docker run -d -p XXX.XXX.XXX.XXX:YYYYY:22 marchandd/term_ssh_root_wine`

All details on [docs](https://github.com/marchandd/term_ssh_root_wine/blob/master/docs/summary.md "Summary")

## Container usage (standalone mode only)

Open terminal with root/administrator account.  
Basic fixed password for Docker public repository = 'term_ssh_root_wine'

:computer: `ssh -X root@XXX.XXX.XXX.XXX -p YYYYY`

All details on [docs](https://github.com/marchandd/term_ssh_root_wine/blob/master/docs/summary.md "Summary")

## Explanations

### Dockerfile

All details on [docs](https://github.com/marchandd/term_ssh_root_wine/blob/master/docs/summary.md "Summary")

### Display

Make sure to have installed OpenSSH client or GUI SSH client (Putty).
Wine is installed but need to be initialized before using it.

### Risks

Root account from container is exposed.  
A password is used and not a certificate that could be more secure.
