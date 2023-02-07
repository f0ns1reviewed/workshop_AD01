
## 1. Dump credentials (resources/Shapkatz.exe) detection
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
### 1.1 Output
![shapkatz output](resources/sharpkatz_output.png)

### 1.2 Evidences

![shapkatz evidences 1](resources/sharpkatz_evidences_1.png)

![shapkatz evidences 2](resources/sharpkatz_evidences_2.png)

![shapkatz evidences 3](resources/sharpkatz_evidences_3.png)

![shapkatz evidence 4](resources/sharpkatz_evidences_4.png)

![shapkatz evidences 5](resources/sharpkatz_evidences_5.png)

![shapkatz evidences 6](resources/sharpkatz_evidences_6.png)

![shapkatz evidences 7](resources/sharpkatz_evidences_7.png)

![shapkatz evidences 8](resources/sharpkatz_evidences_8.png)

![shapkatz evidences 9](resources/shapkatz_evidences_9.png)

![shapkatz evidences 10](resources/sharpkatz_evidences_10.png)

![shapkatz evidences 11](resources/shapkatz_evidences_11.png)

![shapkatz evidences 12](resources/shapkatz_evidences_12.png)



## 2. PassTheHash Laterarl movement

### 2.1 Use mimikatz: f0ns1 (resources/Local System Administrator) --> worker01 (resources/Domain ad.forest.corp user)

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
### 2.2 Output
![pth new terminal](resources/pth_new_terminal.png)
### 2.3 Evidenes

![PassThehash evidences 1](resources/pth_1.png)
![PassThehash evidences 2](resources/pth_2.png)
![PassThehash evidences 3](resources/pth_3.png)
![PassThehash evidences 4](resources/pth_4.png)
![PassThehash evidences 5](resources/pth_5.png)
![PassThehash evidences 6](resources/pth_6.png)
![PassThehash evidences 7](resources/pth_7.png)
![PassThehash evidences 8](resources/pth_8.png)
![PassThehash evidences 9](resources/pth_9.png)
![PassThehash evidences 10](resources/pth10.png)
![PassThehash evidences 11](resources/pth_11.png)
![PassThehash evidences 12](resources/pth_12.png)
![PassThehash evidences 12](resources/pth_13.png)



## 3. Use PSRemoting and access to domain controller (resources/whithout logon)

```
EVTX: 
4648: Session Init
5158: Connection to platform
5158: Connection to platform
```


### 3.2 Output

![PSRemoting worker01](resources/PSRrmoting_worker01.png)

### 3.3 Evidences

![PSRemoting worker01](resources/PSRemoting_1.png)
![PSRemoting worker01](resources/PSRemoting_2.png)
![PSRemoting worker01](resources/PSRemoting_3.png)


