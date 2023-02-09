# Dump Credentials

![Fileless dump credentials](resources/FIleless.png)

## Table of content

  1. [SECURITY EVENTS TRIAGE](#security-events-triage)
  2. [VULNERABILITY DETECTION](#vulnerability-detection)  
  3. [CONSLUSIONS](#conclusions)



## SECURITY EVENTS TRIAGE

### Evidences

After security events triage, the most important evidences could be find on the following list :

```
EVTX:

4104 x251
```

![fileless output](resources/Fileless_mimikatz_1.png)
![fileless output](resources/Fileless_mimikatz_251.png)


## VULNERABILITY DETECTION

There isn't vulnerabilities on this section.


## CONCLUSIONS

The attacker with Administrative rights can dump the Lsass.exe process on the Active Directory server:

![fileless output](resources/Invoke-Mimi_fileless.png)

Maybe, one of these users could belong to the trusted Forest Active directory domain?

![New Target server](resources/new_target_server.png)

![fileless output](resources/Dump.png)


# TO BE CONTINUE ....
