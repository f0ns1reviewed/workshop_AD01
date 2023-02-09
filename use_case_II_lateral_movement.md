## LATERAL MOVEMENT

## Table of content

  1. [SECURITY EVENTS TRIAGE](#security-events-triage)
  2. [VULNERABILITY DETECTION](#vulnerability-detection)  
  3. [CONCLUSIONS](#conclusions)


### SECURITY EVENTS TRIAGE

### Use mimikatz: f0ns1 (resources/Local System Administrator) --> worker01 (resources/Domain ad.forest.corp user)

After security events triage, the most important evidences could be find on the following list:

```
EVTX:
4688: process creation
4673: Use of confidential privilege
4611: Extension of security system
4673: Use of confidential privilege
4624: Session Init
4627: Belong to groups
4672: Special session init
4688: Process creation
4690: Identifiers manipulation
4658, 4656, 4663: Kernel objects
4690: Identifiers manipulation
4658, 4656, 4663: Kernel objects
```
The parent process [powershell.exe] launched by the threat user [f0ns1], execute the child process with the binary mimikatz.exe:

![PassThehash evidences 1](resources/pth_1.png)

The process of the binary [mimikatz.exe] use the privilege SeTcbPrivilege:

![PassThehash evidences 2](resources/pth_2.png)

The [mimikatz.exe] try to manipulate objects:

![PassThehash evidences 10](resources/pth10.png)

![PassThehash evidences 11](resources/pth_11.png)

The process [mimikatz.exe] call to process [lsass.exe]:

![PassThehash evidences 12](resources/pth_12.png)

![PassThehash evidences 12](resources/pth_13.png)

The Operative System launch the Secondary Logon service

![PassThehash evidences 4](resources/pth_4.png)

The process [lsass.exe] use the service LsaRegisterLogonProcess() for authentication process launched by the target worksattion [CLIENT01]:

![PassThehash evidences 5](resources/pth_5.png)

The process [svchost.exe] launched by user [f0ns1] impersonate privileges with user [worker01] that belong to domain ad.forest.corp:

![PassThehash evidences 6](resources/pth_6.png)

Local groups asigned to user [f0ns1] on the workstation [CLIENT01]:

![PassThehash evidences 7](resources/pth_7.png)

Privileges for the user:

![PassThehash evidences 8](resources/pth_8.png)

The parent process [powershell.exe] that launch the child process [mimikatz.exe], finally spawn a new console [cmd.exe] with the [AD\worker01] privileges using a TGS authentication of kerberos:  

![PassThehash evidences 9](resources/pth_9.png)

## VULNERABILITY DETECTION

The threat actor [CLIENT01\insider] using the new local administrator user [CLIENT01\f0ns1], was detected using Pass The hash technique in order to impersonate the user of domain [AD\worker01]:

![pth new terminal](resources/pth_new_terminal.png)

## CONCLUSIONS

There aren't vulnerabilities on this section, but It si possible determine the impersonation of the threat actor to the domain user via [mimikatz.exe] tool:

![conclussions](resources/Conclussions_II.png)





