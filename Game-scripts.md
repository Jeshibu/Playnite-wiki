# Info

All game scripts (including global ones) are executed synchronously and Playnite always waits for a script to completely finish. This means that including code that has blocking execution, for example waiting for process to finish, will lock up Playnite completely until script finishes with execution.

PowerShell is currently the recommended script runtime, given how many features it provides compared to other currently supported runtimes.

# Examples

Starting additional application(s) before game starts and killing it after game exits.

* Edit game and go to `Scripts` tab
* Change runtime to `PowerShell`
* Set first script to start your application using [Start-Process](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/start-process?view=powershell-6) cmdlet
```
Start-Process "c:\somepath\someapp.exe" "-some arguments"
```

* Set second script to kill the application using [Stop-Process](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/stop-process?view=powershell-6) cmdlet

```
Stop-Process -Name "someapp"
```
* If the application requires elevated rights to start then you need to start Playnite as admin too, otherwise the `Stop-Process` will fail due to insufficient privileges.
* If you want to start application minimized and application doesn't have native support for it then add `-WindowStyle` argument.
```
Start-Process "c:\somepath\someapp.exe" "-some arguments" -WindowStyle Minimized
```