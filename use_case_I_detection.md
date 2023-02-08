
# Detection

# Table of Contents

  1. [ENUMERATION](#enumeration)
  2. [PRIVILEGE ESCALATION](#privilege-escalation)


## ENUMERATION

During the enumeration process the attacker used Invi-shell with Powershell. For this reason is not possible detect the enumeration process across the operative system:

[Anex A (resources/Invi-shell studied case)](invi-shell.md)

## PRIVILEGE ESCALATION:

Binary process execution:

![Invishell script](resources/binary_bat.png)

Attack vector:

![Invishell script](resources/permisios_servicio.png)

Modified service:
![Invishell script](resources/modificacion_de_servicio.png)

Evtx evidences:

![Invishell script](resources/servicio_ejecuta_binario_4688.png)

![Invishell script](resources/binario_grupo_admin.png)

![Invishell script](resources/binario_asocia_grupo1.png)
