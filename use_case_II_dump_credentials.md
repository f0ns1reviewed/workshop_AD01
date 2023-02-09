# DUMP CREDENTIALS

## Table of content

  1. [EVIDENCES RECOLECTION](#evidences-recolection)
  2. [EVENTS TRIAGE](#events-triage)
  3. [VULNERABILITY DETECTION](#vulnerability-detection)  
  4. [CONSLUSIONS](#conclusions)


### EVIDENCES RECOLLECTION

In order to perform a forensic analysis the Windows Live Response was executed on the afected server:
[Forensics Tools](Forensics.md)

Extract security events from Operative system:

```
wevtutil.exe epl Security Z:\local_priv.evtx
```

Parse security events:

```
Z:\EvtxECmd\EvtxECmd.exe -f Z:\local_priv.evtx --csv Z:\  --csvf local_priv_events.csv
```
![Parse security events](resources/parse_security_events.png)

Extract System events from Operative system:

```
wevtutil.exe epl System Z:\local_priv_system.evtx
```

Parse System events:

```
Z:\EvtxECmd\EvtxECmd.exe -f Z:\local_priv_system.evtx --csv Z:\  --csvf local_priv_events_system.csv
```
![Parse security events](resources/parse_security_events.png)


### EVENTS TRIAGE
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

## VULNERABILITY DETECTION


## CONSLUSIONS

