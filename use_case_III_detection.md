# Detection
* For this study is requiered update the GPO policy on the target or in the Domain controller with the following configuration:
[Enable Events 4688](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/component-updates/command-line-process-auditing)

This configuration enable the audit of process creation command line with EventID 4688.


## Table of content

  1. [FILELESS ENUMERATION](use_case_III_fileless_enumeration.md)
  2. [FILELESS PRIVESC](use_case_III_fileless_privesc.md)
  3. [FILELESS DUMP CREDENTIALS](use_case_III_fileless_dump_creds.md)  
  
***The recollection process is global, for the previous uses cases:***


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



