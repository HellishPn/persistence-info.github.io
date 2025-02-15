## "Run" and "RunOnce" registry keys


### Location:
- `HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run`
- `HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce`


### Classification:

| Criteria | Value |
|:--- |:---|
| Permissions | User |
| Security context | User |
| Persistence type | Registry |
| Code type | EXE; Other; Fileless |
| Launch type | Same logon required |
| Impact | Non-destructive |
| OS Version | All OS versions |
| Dependencies | OS only |
| Toolset | Scriptable |


### Description:
Well known key, used by many apps. Any file path specified in a Registry value will be used to `ShellExecute()` the specified file by explorer.exe when user logs on. Multiple values can exist.
>  The Run key makes the program run every time the user logs on, while the RunOnce key makes the program run one time, and then the key is deleted.
Evasion TIP : using c:\windows\system32\cmd.exe /c start %windir%\system32\SecurityHealthSystray.exe && C:\..\..\Malware.exe , this the OLD SYSinternals Autoruns can't detect it and NEW version shows CMD
Evasion Tip : Using c:\windows\system32\cmd.exe /c start %windir%\system32\SecurityHealthSystray.exe && c:\windows\Explorer.exe C:\..\..\Malware.exe, you can change the Parent child relashionship which is SySinternals Process Explorer can't detect anything suspicious

### References:
- <https://docs.microsoft.com/en-us/windows/win32/setupapi/run-and-runonce-registry-keys>
- <http://windowsir.blogspot.com/2022/07/does-autostart-really-mean-autostart.html>


### Credits:
N/A


### See also:
<!-- - [HKLM `Run` and `RunOnce` registry keys](hklmrun.html) -->


### Remarks:
