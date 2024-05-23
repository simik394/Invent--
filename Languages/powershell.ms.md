
Get-ChildItem Env:

```powershell
[System.Environment]::SetEnvironmentVariable("MY_VARIABLE", "Hello, World!", "Machine")
```

```powershell
$global:myGlobalVariable = "Hello, World!"
```

