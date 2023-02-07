# DUMP EVTX form machine


```
PS C:\Windows\system32> wevtutil el | ForEach-Object {   $file=$_.Replace(resources/"/","_"); wevtutil.exe epl $_ "Y:\CLIENT01_202
30202_173838\DUMP_ALL_EVTX\$file.evtx" }

```


# PARSING EVTX

```
PS Y:\chainsaw>  Get-ChildItem -Path Y:\CLIENT01_20230202_173838\DUMP_ALL_EVTX\ | Select Name | ForEach-Object { $file =
 $_.Name;.\EvtxECmd\EvtxECmd.exe -f Y:\CLIENT01_20230202_173838\DUMP_ALL_EVTX\$file --csv "Y:\CLIENT01_20230202_173838\"
 --csvf $file.Replace(resources/"evtx","csv") }
```
