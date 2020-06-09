| Title            | LP_0109_windows_powershell_script_block_logging                                                                     |
|:-----------------|:--------------------------------------------------------------------------------|
| **Author**       | @atc_project                                                                      |
| **Description**  | Script block logging records blocks of code as they are executed by the PowerShell engine,  thereby capturing the full contents of code executed by an attacker, including scripts and commands.  Due to the nature of script block logging, it also records de-obfuscated code as it is executed.  PowerShell 5.0 will automatically log code blocks if the block’s contents match on a list of suspicious commands or scripting techniques,  even if script block logging is not enabled. These suspicious blocks are logged at the “warning” level in EID 4104,  unless script block logging is explicitly disabled.                                                               |
| **Default**      | Partially (Other)                                                                   |
| **Event Volume** | High                                                                    |
| **EventID**      | <ul><li>4104</li></ul>         |
| **References**   | <ul><li>[https://www.fireeye.com/blog/threat-research/2016/02/greater_visibilityt.html](https://www.fireeye.com/blog/threat-research/2016/02/greater_visibilityt.html)</li></ul> |



## Configuration

Manual steps to implement logging policy:

```
Computer Configuration > 
Administrative Templates > 
Windows PowerShell > 
Turn on PowerShell Script Block Logging (Enable)
```

Enabling via registry key:
```
reg add "hklm\SOFTWARE\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" /v EnableScriptBlockLogging /t REG_DWORD /d 1
```


