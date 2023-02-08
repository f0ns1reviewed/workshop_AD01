# Invisi-shell

Table of content:

  1. [DESCRIPTION](#description)
  2. [HOW IT WORKS](#how-it-works)
  3. [BYPASS AMSI DEFENDER AUDIT EVTX](#bypass-amsi-defender-audit-evtx)
  4. [SOURCE CODE ANALISYS](#source-code-analisys)
  5. [IOCS](#iocs)
  6. [COMPLEMENTARY INFORMATION](#complementary-information)

## DESCRIPTION

```
Hide your powershell script in plain sight! Invisi-Shell bypasses all of Powershell security features and Opertive system audit (powershell)
```

## HOW IT WORKS

The Invisi-shell project should be launched from an specific process on the windows operative system:

```
  1.cmd.exe
  2.powrshell.exe
```
There are two different ways to launch the Invisi-shell project, with Administrative or non-administrative privileges. The project should be launched using the following scripts:

```
  1.Admin: RunWithPathAsAdmin.bat
  2.Not Admin: RunWithRegistryNonAdmin.bat
 ```
The both previous "bat" scripts prepare the Operating system for the execution of the child process Powershell.
The communication functions of the child process related with AMSI validation and Operative system Audit are hooked by the InvisiShellProfiler.dll dynamic library, using the public windows [System.Management.Automation] and [System.Core] libraries.

![How Invishell Works](resources/Invisshell_how_it_works.png)

This is a bat script example, that prepare the operative system loading dynamic library in the windows register:

![Invishell script](resources/invishell.png)

Operative system registers validation:

![Invishell registers](resources/Invishell_reg.png)


## BYPASS AMSI DEFENDER AUDIT EVTX

How Invisi-shell works across the windows AMSI architecture:

![Amsi bypass](resources/invi-shell_bypass.png)

AMSI architecture invocation level (SW):

![Amsi Architecture sw level](https://1.bp.blogspot.com/-AdO9FunaUBY/Wt2YS4wpIQI/AAAAAAAAJc8/yqSgf4L2PbMpHxgXePMYsqS3UXhL1dZ2wCLcBGAs/s1600/amsi4.png)

The following evidence validate the the Windows Defender is active across the Operative System:

![Invishell script](resources/evtx_defender.png)

## SOURCE CODE ANALISYS

The original source code is aviable on the following github repository:

[Invi-shell (resources/Repository)](https://github.com/OmerYa/Invisi-Shell)

Personal analysis of software architecture and hooked functions of powershell by Invisi-shell:

![Source Code Analisys](resources/Source_code_analisys.png)

Hooked functions:

| Package |	Class |	Function|
|---------|-------|---------|
| System.Management.Automation	| AmsiUtils	| ScanContent |
| System.Management.Automation	| ScriptBlock	| WriteScriptBlockToLog |
| System.Management.Automation	| ScriptBlock	| LogScriptBlockStart |
| System.Management.Automation	| ScriptBlock	| LogScriptBlockEnd |
| System.Management.Automation	| EventLogLogProvider	| LogEvent |
| System.Management.Automation.Tracing	| PSEtwLogProvider	| WriteEvent |
| System.Management.Automation.Host	| TranscriptionOption	| FlushContentToDisk |
| System.Management.Automation	| ExecutionContext	| get_LanguageMode |
| System.Management.Automation	| ExecutionContext	| get_HasEverUsedConstrainedLanguage |
| System.Management.Automation	| ExecutionContext	| get_HasRunspaceEverUsedConstrainedLanguageMode |
| System.Management.Automation	| ExecutionContext	| set_LanguageMode |
| System.Diagnostics.Eventing.EventProvider	| EventProvider	| WriteTransferEvent |


## IOCS

```
Register: 
-Harcoded unique identifier object: {cf0d821e-299b-5307-a3d8-b283c03916db}
dll name: 
-InvisiShellProfiler.dll
```

### COMPLEMENTARY INFORMATION

[AMSI-Powershell bypass](https://www.mdsec.co.uk/2018/06/exploring-powershell-amsi-and-logging-evasion/)

[Microsoft ](https://learn.microsoft.com/es-es/windows/win32/amsi/how-amsi-helps)

[Rasta-mouse](https://github.com/rasta-mouse/AmsiScanBufferBypass)

[Rasta.mouse](https://rastamouse.me/memory-patching-amsi-bypass/)

[PoC f0ns1](https://github.com/f0ns1/antivirus_bypass_powershell)
