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



### 1.3 Fileless Privilege Escalation

### Output
![Autologon credentials](resources/Autologon_vuln.png)
### Evidences

```
RegRipper

```


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


# 2 Dump Credentials

### Output
![fileless output](resources/Invoke-Mimi_fileless.png)

![fileless output](resources/Dump.png)

### Evidences

```
EVTX:

```

![fileless output](resources/Fileless_mimikatz_1.png)
![fileless output](resources/Fileless_mimikatz_251.png)
