
## Table of content

  1. [EVIDENCES RECOLECTION](#evidences-recolection)
  2. [EVENTS TRIAGE](#events-triage)
  3. [VULNERABILITY DETECTION](#vulnerability-detection)  
  4. [CONSLUSIONS](#conclusions)


# 1. Privilege Escalation

## 1.2 Fileless Enumeration

### Output
![fileless output](resources/Fileless_ActiveDirectory.png)

### Evidences

Windows Active Directory side (resources/powershell enumeration):
```
EVTX:
4104 x 49

```
![fileless Load_powerup](resources/fileless_load_1.png)

![fileless Load_powerup](resources/fileless_load_1.png)

Windows client side (resources/python server):
```
EVTX:
5156

```
![Python Server](resources/python_server.png)
