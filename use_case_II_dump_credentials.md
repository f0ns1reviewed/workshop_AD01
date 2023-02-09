# DUMP CREDENTIALS

## Table of content

  1. [SECURITY EVENTS TRIAGE](#security-events-triage)
  2. [VULNERABILITY DETECTION](#vulnerability-detection)  
  3. [CONCLUSIONS](#conclusions)


### SECURITY EVENTS TRIAGE

After security events triage, the most important evidences could be find on the following list:

```
EVTX: 
4688: Process execution 
4673: Use of confidential privilege
4690: Identifiers manipulation
4658, 4653,4663, 4658: Kernel Objects access 
4690: Identifiers manipulation
4658, 4653, 4663: kernel Object access
4689: End of processs
```
The Parent process of the threat actor [powershell], create a child process that invoke the binary [SharpKatz.exe]:

![shapkatz evidences 1](resources/sharpkatz_evidences_1.png)

The [Sharpkatz.exe] process set the operative system privilege SeCreateGlobalPrivilege:

![shapkatz evidences 2](resources/sharpkatz_evidences_2.png)

Identifiers manipulation by origin process [0x11b0] SharpKatz.exe over external process [0x4]:

![shapkatz evidence 4](resources/sharpkatz_evidences_4.png)

The [0x11b0] SharpKatz.exe try to access to [0x2b0] LSASS process, with the following privileges:

![shapkatz evidences 5](resources/sharpkatz_evidences_5.png)

![shapkatz evidences 6](resources/sharpkatz_evidences_6.png)

Access to kernel object by [0x11b0] SharpKatz.exe:

![shapkatz evidences 7](resources/sharpkatz_evidences_7.png)

![shapkatz evidences 8](resources/sharpkatz_evidences_8.png)

![shapkatz evidences 9](resources/shapkatz_evidences_9.png)

![shapkatz evidences 10](resources/sharpkatz_evidences_10.png)

![shapkatz evidences 11](resources/shapkatz_evidences_11.png)

![shapkatz evidences 12](resources/shapkatz_evidences_12.png)

## VULNERABILITY DETECTION

One of domain users [AD\worker01] was logged on the target server and the account've never been logoff, for this reason an authenticated local user with Administrator privileges on the workstation could dump the LSASS process of the Operative System.
This process contains on dynamic memory, the plaintext credentials and ntlm hash of the user:

![shapkatz output](resources/sharpkatz_output.png)

## CONCLUSIONS

  1.  The local user [insider] spawn a terminal 
  2.  The terminal belong to [f0ns1] local user Administrator. 
  3.  After dump  credentials the [f0ns1] could impersonate to domain user [AD\worker01]


![conclussions](resources/Conclussions_II.png)
