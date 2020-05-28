| Title            | LP_0108_windows_powershell_module_logging                                                                     |
|:-----------------|:--------------------------------------------------------------------------------|
| **Description**  | Module logging records pipeline execution details as PowerShell executes,  including variable initialization and command invocations.  Module logging will record portions of scripts, some de-obfuscated code,  and some data formatted for output.  This logging will capture some details missed by other PowerShell logging sources,  though it may not reliably capture the commands executed                                                               |
| **Default**      | Not configured                                                                   |
| **Event Volume** | High                                                                    |
| **EventID**      | <ul><li>4103</li></ul>         |
| **References**   | <ul><li>[https://www.fireeye.com/blog/threat-research/2016/02/greater_visibilityt.html](https://www.fireeye.com/blog/threat-research/2016/02/greater_visibilityt.html)</li></ul> |



## Configuration

Manual steps to implement logging policy:

```
Computer Configuration > 
Administrative Templates > 
Windows PowerShell > 
Turn on Module Logging (Enable)
```
To specify modules which should be logged set them in `Show...` dialog. Wildcards are supported.

Enabling via registry key:
```
reg add "hklm\SOFTWARE\Policies\Microsoft\Windows\PowerShell\ModuleLogging" /v EnableModuleLogging /t REG_DWORD /d 1
reg add "hklm\SOFTWARE\Policies\Microsoft\Windows\PowerShell\ModuleLogging\ModuleNames" /v "*" /t REG_SZ /d "*"
```


