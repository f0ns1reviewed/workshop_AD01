## Fileless Privilege Escalation

## Table of content

  1. [SECURITY EVENTS TRIAGE](#security-events-triage)
  2. [VULNERABILITY DETECTION](#vulnerability-detection)  
  3. [CONSLUSIONS](#conclusions)

## SECURITY EVENTS TRIAGE
## Table of content

  1.1 [CREDENTIALS DETECTION](#credentials-detection)
  
  1.2 [PSRemoting ACCESS](#psremoting-access) 

### CREDENTIALS DETECTION

### Evidences

In this section, on the Windows registry server path at HK Local Machine:

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
```
It's possible to detect the specific values for the properties:

```
DefaultUserName
DefaultUserPassword
```
Defined by the Adminsitrator.

In order to perform a forensic analysis the Windows RegistryExplorer was executed on the afected server:
[Forensics Tools](Forensics.md)

Default user credentials:
![Autologon User](resources/Reg_ripper_autologon_1.png)

Default user Password:
![Autologon Password](resources/Reg_ripper_autologon_2.png)


### PSRemoting ACCESS

### Evidences
After security events triage, the most important evidences could be find on the following list :
```
EVTX:
4672
4624
4627
```
New session created on the Active directory server for an Administrator user:

![Logon 2](resources/Login_2.png)

Validate assigned groups for the Administrator user:

![Logon 3](resources/Logon_3.png)

The server assign the permissions of the groups that the Administrator user belong:

![Logon 1](resources/Logon_1.png)

## VULNERABILITY DETECTION

The Default Autologon in the Operative System, allow to an attacker obtain the username and credentials on plaintext:

![Autologon credentials](resources/Autologon_vuln.png)

## CONCLUSIONS 

Configure a target server with Autologon credentials it's a Vulnerability, because any authenticate user could obtain it from registry
