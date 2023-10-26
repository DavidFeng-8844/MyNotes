
## 27/10/2023

>Terminal error:
>Can't use conda activate but conda init is still usable

>Possible Cause:
>related to the PowerShell execution policy, which is a security feature that determines what type of scripts can be run on your system. By default, PowerShell is set to Restricted, which means that scripts are not allowed to run.

switch to administrator powershell
```command
Start-Process -FilePath "Powershell" -Argumentlist "Start-Process powershell -Verb RunAs" -Wait
```

Then Set the execution policy to a more permissive level.
```
Set-ExecutionPolicy RemoteSigned
```



 