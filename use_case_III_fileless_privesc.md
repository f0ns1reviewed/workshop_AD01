## Fileless Privilege Escalation

## Table of content

  1. [SECURITY EVENTS TRIAGE](#events-triage)
  2. [VULNERABILITY DETECTION](#vulnerability-detection)  
  3. [CONSLUSIONS](#conclusions)

## SECURITY EVENTS TRIAGE
### Evidences

```
Using Windows Registry
```
Default user credentials:
![Autologon User](resources/Reg_ripper_autologon_1.png)

Default user Password:
![Autologon Password](resources/Reg_ripper_autologon_2.png)

## VULNERABILITY DETECTION

### Output
![Autologon credentials](resources/Autologon_vuln.png)


### 1.4 PSRemoting

### Output
![fileless output](resources/psremoting_output.png)
### Evidences

```
EVTX:

```
![Logon 1](resources/Logon_1.png)
![Logon 2](resources/Login_2.png)
![Logon 3](resources/Logon_3.png)

## CONCLUSIONS 

