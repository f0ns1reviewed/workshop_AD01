
# Detection

# Table of Contents

  1. [ENUMERATION](#enumeration)
  2. [PRIVILEGE ESCALATION](#privilege-escalation)


## ENUMERATION

During the enumeration process the attacker used Invi-shell with Powershell. For this reason is not possible detect the enumeration process across the operative system:

[Anex A (resources/Invi-shell studied case)](invi-shell.md)

## PRIVILEGE ESCALATION:

## Table of content

  1. [EVIDENCES RECOLECTION](#evidences-recolection)
  2. [EVENTS TRIAGE](#events-triage)
  3. [TIMELINE PROCESS EXECUTION](#timeline-process-execution)
  4. [VULNERABILITY DETECTION](#vulnerability-detection)  

### EVIDENCES RECOLECTION

In order to perform aforensics analysis the Windows Live Response was executed on the afected server:
[Forensics Tools](Forensics.md)


### EVENTS TRIAGE

Binary process execution:

![Invishell script](resources/binary_bat.png)


Evtx evidences:


![Invishell script](resources/servicio_ejecuta_binario_4688.png)

![Invishell script](resources/binario_grupo_admin.png)

![Invishell script](resources/binario_asocia_grupo1.png)


### TIMELINE PROCESS EXECUTION

### VULNERABILITY DETECTION 

Detected attack vector:

```
The target service execute a binary process that could be modified for all authenticated users at the operative system.

```

![Invishell script](resources/permisios_servicio.png)

The source code of the modified service, after and before the threat actor access to the oeprative system:

![Invishell script](resources/modificacion_de_servicio.png)

